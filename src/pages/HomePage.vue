<template>
  <div>
      <slider-section/>
      <our-best-work/>
      <our-services/>
      <footer-section/>
  </div>
</template>

<script>
import SliderSection from '../components/SliderSection'
import OurServices from '../components/OurServices'
import OurBestWork from '../components/OurBestWork'
import FooterSection from '../components/FooterSection'

export default {
    components: {
        SliderSection,
        OurServices,
        OurBestWork,
        FooterSection
    }
}
</script>

<style>

</style>