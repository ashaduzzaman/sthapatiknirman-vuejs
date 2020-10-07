<template>
  <div class="mt-10">
      <v-layout>
          <v-flex>
              <div class="title">Latest Feed</div>
          </v-flex>
          <v-flex text-right>
              <v-btn icon>
                  <v-icon>mdi-menu</v-icon>
              </v-btn>
              <v-btn color="red" icon>
                  <v-icon>mdi-view-grid-outline</v-icon>
              </v-btn>
          </v-flex>
      </v-layout>
      <v-row class="mt-5">
          <v-col v-for="(image,i) in feedImages" :key="i">
            <v-card elevation="12" width="210" height="230" color="blue" class="mr-5">
              <v-img height="230" :src="image"></v-img>
            </v-card>
          </v-col>
      </v-row>
  </div>
</template>

<script>
export default {
    data:() => ({
        feedImages: [
            "https://images.unsplash.com/photo-1600745644600-20436d748941?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=634&q=80",
            "https://images.unsplash.com/photo-1600748914826-67de972c3dca?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=634&q=80",
            "https://images.unsplash.com/photo-1600497934937-2d02ebad5da3?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=634&q=80",
            "https://images.unsplash.com/photo-1600631965708-89abd5b68ab9?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=634&q=80",
            "https://images.unsplash.com/photo-1600749452451-edca03cbe0d9?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=564&q=80",
            "https://images.unsplash.com/photo-1600718096300-5e9fc80ff942?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=634&q=80"
        ]
    }),
}
</script>

<style>

</style>