<template>
  <v-container>
      <v-layout class="pa-10 mt-5">
          <v-flex text-center>
              <div class="section-subtitle title">Our Services</div>
              <h2 class="section-title"><b>WE PROVIDE</b> THE BEST SERVICES</h2>
              <div class="theme-separator-line-horrizontal-full"></div>
          </v-flex>
      </v-layout>
        <!-- <v-row style="position:relative; position: 0 auto; width:100%;">
            <v-col class="mx-auto" v-for="i in 4" :key="i">
                <v-hover v-slot:default="{ hover }">
                    <v-card class="mr-2 pa-4" color="grey lighten-4" elevation="12" width="410" height="410">
                        <v-img height="190" src="https://cdn.vuetifyjs.com/images/cards/kitchen.png">
                            <v-expand-transition>
                                <div v-if="hover" class="d-flex transition-fast-in-fast-out orange darken-2 v-card--reveal display-3 white--text" style="height: 100%;"> $14.99 </div>
                            </v-expand-transition>
                        </v-img>
                        <v-card-text class="pt-6" style="position: relative;">
                            <h3 class="display-1 font-weight-light orange--text mb-2">QW cooking utensils</h3>
                            <div class="font-weight-light title mb-2"> Our Vintage kitchen utensils delight any chef.<br> Made of bamboo by hand </div>
                        </v-card-text>
                    </v-card>
                </v-hover>
            </v-col>
        </v-row> -->
        <v-container fluid>
        <v-row dense class="mt-5 ml-10 mr-10">
          <v-col v-for="(image,i) in feedImages" :key="i" class="card-hover">
              <!-- <v-hover v-slot:default="{ hover }"> -->
                <v-card
                    class="mx-auto"
                    max-width="344"
                >
                    <v-img
                    :src="image"
                    height="200px"
                    >
                    </v-img>

                    <v-card-title>
                    Top western road trips
                    <v-spacer></v-spacer>

                    <v-btn
                        icon
                        @click="show = !show"
                    >
                        <v-icon>{{ show ? 'mdi-chevron-up' : 'mdi-chevron-down' }}</v-icon>
                    </v-btn>
                    </v-card-title>

                    <v-expand-transition>
                    <div v-show="show">
                        <v-divider></v-divider>

                        <v-card-text>
                        I'm a thing. But, like most politicians, he promised more than he could deliver. You won't have time for sleeping, soldier, not with all the bed making you'll be doing. Then we'll go with that data file! Hey, you add a one and two zeros to that or we walk! You're going to do his laundry? I've got to find a way to escape.
                        </v-card-text>
                    </div>
                    </v-expand-transition>
                </v-card>
            <!-- </v-hover> -->
          </v-col>
        </v-row>
        </v-container>
  </v-container>
</template>

<script>
export default {
    data:() => ({
        feedImages: [
            "https://images.unsplash.com/photo-1600745644600-20436d748941?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=634&q=80",
            "https://images.unsplash.com/photo-1600748914826-67de972c3dca?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=634&q=80",
            "https://images.unsplash.com/photo-1600497934937-2d02ebad5da3?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=634&q=80",
            "https://images.unsplash.com/photo-1600631965708-89abd5b68ab9?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=634&q=80",
        ],
        show: false,
    }),
}
</script>

<style>
.section-subtitle{
    font-size: 1rem;
    font-weight: 600;
    color: #878e94;
    margin: 0;
    padding: 0 0 0.313rem;
}
.section-title{
    margin: 0rem;
    font-size: 3rem;
    line-height: 1.3;
    font-weight: 400;
    text-transform: uppercase;
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
.card-hover {
  transition: transform 1s;
}

.card-hover:hover {
  transform: translate(0px, -20px);
}
</style>