<template>
  <div>
    <v-carousel 
      cycle
      hide-delimiters
      show-arrows-on-hover
      :interval="interval"
    >
        <v-carousel-item
          v-for="item in banner_data"
          :key="item.id"
          :src = "image_base_url+item.image_path"
          eager
          transition="slide-y-reverse-transition"
          reverse-transition="scale-transition"
        >
        </v-carousel-item>
        <div class="l-section-overlay"></div>
    </v-carousel>
  </div>
</template>

<script>
export default {
      props: ['banner_data'],
    data: () => ({
      sticky: true,
      interval: 2000,
      image_base_url: "",
    }),
    created(){
      this.image_base_url = process.env.VUE_APP_IMG_URL;
    }
}
</script>

<style>
.centered {
  position: absolute;
  font-size:59px;
  line-height: 1.2em;
  letter-spacing: -.8px;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

@media only screen and (min-width: 960px) {
        /* styles for browsers larger than 960px; */
  .v-carousel{
    height: 300px !important;
  }
  .v-carousel .v-carousel__item{
    height: 300px !important;
    background: rgba(0, 0, 0, 0.5);
  }
}
@media only screen and (min-width: 1440px) {
    /* styles for browsers larger than 1440px; */
  .v-carousel{
    height: 550px !important;
  }
  .v-carousel .v-carousel__item{
    height: 550px !important;
    background: rgba(0, 0, 0, 0.5);
  }
}
@media only screen and (min-width: 2000px) {
    /* for sumo sized (mac) screens */
    .v-carousel{
  height: 600px !important;
  }
  .v-carousel .v-carousel__item{
    height: 600px !important;
    background: rgba(0, 0, 0, 0.5);
  }
}

.l-section-overlay {
    background-color: rgba(0,0,0,0.4);
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
}
</style>