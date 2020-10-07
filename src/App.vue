<template>
  <v-app>
    <!-- <v-navigation-drawer v-model="sidebar" app>
      <v-list>
        <v-list-item v-for="item in menuItems" :key="item.title" :to="item.path">
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>{{ item.title }}</v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer> -->

    <v-app-bar 
      flat 
      dark 
      shrink-on-scroll
      prominent 
      dense 
      app 
      class="pl-5 pr-5"
    >
      
      <!-- <v-toolbar-title> -->
          <img
            src="@/assets/instagram.png"
            alt="RTS ENVIRONMENTAL SERVICES, INC."
            class="mt-4 hidden-sm-and-down"
            width="100"
          />
          <img
            src="@/assets/instagram.png"
            alt="RTS ENVIRONMENTAL SERVICES, INC."
            class="mt-3 hidden-md-and-up"
            height="30px"
          />
      <!-- </v-toolbar-title> -->
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
      <HomePage/>
    </v-main>
  </v-app>
</template>

<script>
// import HelloWorld from './components/HelloWorld';
// import ProfilePage from './pages/ProfilePage'
// import MainNav from './components/MainNav'
import HomePage from './pages/HomePage'
// import ProfileRightNav from './components/ProfileRightNav'

export default {
  name: 'App',

  components: {
    // ProfilePage,
    HomePage,
    // MainNav,
    // ProfileRightNav
  },

  data: () => ({
    menuItems:[
      {title: 'Home', path:'/'},
      {title: 'Portfolio', path:'/portfolio'},
      {title: 'About Us', path:'/about-us'},
    ]
  }),
};
</script>
