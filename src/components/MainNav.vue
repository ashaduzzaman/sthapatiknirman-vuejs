<template>
  <v-navigation-drawer color="grey lighten-5" v-model="drawer" permanent expand-on-hover bottom app>
      <v-layout class="">
        <v-flex>
          <div class="pa-4">
          <v-img width="100px" src="../assets/instagram.png"></v-img>
          </div>
        </v-flex>
      </v-layout>
      <!-- <v-layout class="mt-10">
        <v-flex>
          <v-layout>
            <v-flex text-center>
              <v-avatar size="70" color="grey">
                <v-img src="https://images.unsplash.com/photo-1544005313-94ddf0286df2?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=634&q=80"></v-img>
              </v-avatar>
              <div class="mt-4 title">Štefan Štefančík</div>
              <div class="mt-1 subtitle-2 grey--text">Toronto, Canada</div>
              <div class="mt-5">
                <v-layout>
                  <v-flex>
                    <div class="subtitle-2">Post</div>
                    <div class="subtitle-2 grey--text">520</div>
                  </v-flex>
                  <v-flex>
                    <div class="subtitle-2">Followers</div>
                    <div class="subtitle-2 grey--text">5.2 M</div>
                  </v-flex>
                  <v-flex>
                    <div class="subtitle-2">Following</div>
                    <div class="subtitle-2 grey--text">52</div>
                  </v-flex>
                </v-layout>
              </div>
            </v-flex>
          </v-layout>
        </v-flex>
      </v-layout> -->
      <v-list
        nav
        dense
        class="mt-10"
      >
        <v-list-item-group
          v-model="group"
          active-class="red--text text--accent-2"
        >
          <v-list-item>
            <v-list-item-icon>
              <v-icon>mdi-home-outline</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Feed</v-list-item-title>
          </v-list-item>
          <v-list-item>
            <v-list-item-icon>
              <v-icon>mdi-compass-outline</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Explore</v-list-item-title>
          </v-list-item>
          <v-list-item>
            <v-list-item-icon>
              <v-icon>mdi-pound</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Trending</v-list-item-title>
          </v-list-item>
          <v-list-item>
            <v-list-item-icon>
              <v-icon>mdi-check-decagram</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Top Post</v-list-item-title>
          </v-list-item>
          <v-list-item>
            <v-list-item-icon>
              <v-icon>mdi-account-outline</v-icon>
            </v-list-item-icon>
            <v-list-item-title>People</v-list-item-title>
          </v-list-item>
          <v-list-item>
            <v-list-item-icon>
              <v-icon>mdi-bell-outline</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Notification</v-list-item-title>
          </v-list-item>
          <v-list-item>
            <v-list-item-icon>
              <v-icon>mdi-send-outline</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Direct</v-list-item-title>
          </v-list-item>
          <v-list-item>
            <v-list-item-icon>
              <v-icon>mdi-chart-pie</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Status</v-list-item-title>
          </v-list-item>
          <v-list-item>
            <v-list-item-icon>
              <v-icon>mdi-cog-outline</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Settingst</v-list-item-title>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
</template>

<script>
export default {
    data: () => ({
    drawer: false,
      group: null,
  }),
  watch: {
      group () {
        this.drawer = false
      },
    },
}
</script>

<style>

</style>