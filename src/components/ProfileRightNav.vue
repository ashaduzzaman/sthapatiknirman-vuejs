<template>
  <v-navigation-drawer class="pa-4 mt-6" v-model="drawer" permanent app right clipped floating>
      <v-layout>
        <v-card height="300" width="100%">
            <v-img height="300" width="100%" src="https://images.unsplash.com/photo-1544005313-94ddf0286df2?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=634&q=80"></v-img>
        </v-card>
      </v-layout>
      <v-layout class="mt-6">
        <div class="title">Štefan Štefančík</div>
      </v-layout>
      <v-layout>
          <v-flex>
              <v-layout>
              <div class="subtitle-2">
                  884
              </div>
              <div class="subtitle-2 ml-2 grey--text">Photos</div>
              </v-layout>
          </v-flex>
          <v-flex>
              <v-layout>
              <div class="subtitle-2">
                  524k
              </div>
              <div class="subtitle-2 ml-2 grey--text">Followers</div>
              </v-layout>
          </v-flex>
      </v-layout>
      <v-layout class="mt-4 subtitle-2 grey--text">
        Štefan Štefančík is a freelance model worked for 5 years.
        <br>
        <br> Moved to South Korea 7 years ago for college and now working
      </v-layout>
      <v-layout class="mt-4">
        <v-flex>
          <div class="subtitle-2">Locations</div>
          <div class="subtitle-2 grey--text">Based in Ceder Rapids, IA</div>
        </v-flex>
      </v-layout>
      <v-layout class="mt-4">
        <v-flex>
          <div class="subtitle-2">Profession</div>
          <div class="subtitle-2 grey--text">Modeling</div>
        </v-flex>
      </v-layout>
    </v-navigation-drawer>
</template>

<script>
export default {

}
</script>

<style>

</style>