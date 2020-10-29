<template>
  <v-app>
    <v-navigation-drawer v-model="sidebar" app temporary class='mt-5' style='top: 50px' dark right>
      <v-list>
        <v-list-item v-for="item in menuItems" :key="item.title" :to="item.path">
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>{{ item.title }}</v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar 
      flat 
      dark
      dense 
      app 
      class="pl-5 pr-5"
      height="70"
    >
      
          <img
            src="@/assets/logo.png"
            alt="Sthapatik Nirman"
            class="mx-2 hidden-sm-and-down"
            max-width="40"
            max-height="40"
          />
          <img
            src="@/assets/logo.png"
            alt="Sthapatik Nirman"
            class="mx-2 hidden-md-and-up"
            max-width="30"
            max-height="30"
          />
      <v-toolbar-title>
        Sthapatik Nirman
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-toolbar-items class="hidden-xs-only">
        <v-btn text v-for="item in menuItems" :key="item.title" :to="item.path">
          <!-- <v-icon left dark>{{ item.icon }}</v-icon> -->
          {{ item.title }}
        </v-btn>
      </v-toolbar-items>
      <span class="hidden-sm-and-up">
        <v-app-bar-nav-icon @click="sidebar = !sidebar"></v-app-bar-nav-icon>
      </span>
    </v-app-bar>
    <!-- <main-nav/> -->
    <!-- <profile-right-nav /> -->
    <v-main>
      <!-- <ProfilePage/> -->
      <!-- <HomePage/> -->
      <router-view/>
    </v-main>
      <footer-section/>
  </v-app>
</template>

<script>
import FooterSection from './components/FooterSection'
// import HelloWorld from './components/HelloWorld';
// import ProfilePage from './pages/ProfilePage'
// import MainNav from './components/MainNav'
// import HomePage from './pages/HomePage'
// import ProfileRightNav from './components/ProfileRightNav'

export default {
  name: 'App',

  components: {
        FooterSection
    // ProfilePage,
    // HomePage,
    // MainNav,
    // ProfileRightNav
  },

  data: () => ({
    sidebar: false,
    menuItems:[
      {title: 'Home', path:'/'},
      {title: 'Portfolio', path:'/portfolio'},
      {title: 'Contact', path:'/contact'},
      {title: 'About Us', path:'/about-us'},
    ]
  }),
};
</script>

<style>

a.v-btn--active.v-btn--router{
  background-color:#ffc13b !important;
  color: black;
}

a.v-btn.v-btn--router:after {
    content: "";
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100%;
    height: 100%;
    transform: scaleY(0);
    transform-origin: top center;
    background: #ffc13b;
    z-index: -1;
    transition: transform 0.5s;
}

a.v-btn.v-btn--router:hover::after{
  transform: scaleY(1);
}

.v-list .v-list-item--active {
  background-color:#ffc13b !important;
  color: black !important;
}

.v-toolbar__title{
  font-family: cursive;
}

.theme-separator-line-horrizontal-full {
    background-color: #ffc13b;
    width: 100%;
    height: 0.25rem;
    width: 5.25rem;
    float: none;
    margin-left: auto;
    margin-right: auto;
    margin-top: 0.938rem;
}

.section-title{
    margin: 0rem;
    font-size: 2rem;
    line-height: 1.3;
    font-weight: 300;
    text-transform: uppercase;
}

.card-hover {
  transition: transform 1s;
}

.card-hover:hover {
  transform: translate(0px, -20px);
}

.v-card--reveal {
    align-items: center;
    bottom: 0;
    justify-content: center;
    opacity: .5;
    position: absolute;
    width: 100%;
}

.v-application--wrap {
    min-height: 100vh;
    justify-content: center;
}
</style>
