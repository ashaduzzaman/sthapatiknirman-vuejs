<template>
  <div>
      <slider-section :banner_data = "banner_data"/>
      <our-best-work :best_work_data="best_work_data"/>
      <our-services/>
  </div>
</template>

<script>
import SliderSection from '../components/SliderSection'
import OurServices from '../components/OurServices'
import OurBestWork from '../components/OurBestWork'

export default {
    components: {
        SliderSection,
        OurServices,
        OurBestWork,
    },
    data: () => ({
        banner_data : "",
        best_work_data : ""
    }),
    async created(){
        await this.axios.get(process.env.VUE_APP_API_URL+'/banner-photos-gallery').then((response) => {
            this.banner_data = response.data;
        });
        await this.axios.get(process.env.VUE_APP_API_URL+'/recent-project').then((response)=> {
            this.best_work_data = response.data;
        });
    }

}
</script>

<style>

</style>