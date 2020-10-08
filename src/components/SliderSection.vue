<template>
  <div>
    <v-carousel 
      cycle
      hide-delimiters
      show-arrows-on-hover
      :interval="interval"
    >
        <v-carousel-item
          v-for="(item, i) in items"
          :key="i"
          :src = "item.src"
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
    data: () => ({
      sticky: true,
      interval: 1800,
      items: [
          {
            src: "https://images.unsplash.com/photo-1535406208535-1429839cfd13?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1355&q=80",
          },
          {
            src: 'https://images.unsplash.com/photo-1554941071-8ec75d5379b5?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1350&q=80',
          },
          {
            src: 'https://images.unsplash.com/photo-1554941426-e9604e34bc94?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1350&q=80',
          },
          {
            src: 'https://images.unsplash.com/photo-1593016250787-edf25b355001?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1350&q=80',
          },
        ],
    }),
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
    height: 350px !important;
  }
  .v-carousel .v-carousel__item{
    height: 350px !important;
    background: rgba(0, 0, 0, 0.5);
  }
}
@media only screen and (min-width: 1440px) {
    /* styles for browsers larger than 1440px; */
  .v-carousel{
    height: 600px !important;
  }
  .v-carousel .v-carousel__item{
    height: 600px !important;
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