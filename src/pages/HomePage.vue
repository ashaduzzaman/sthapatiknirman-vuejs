<template>
  <div>
      <banner-section/>
      <our-best-work/>
      <our-services/>
      <footer-section/>
  </div>
</template>

<script>
import BannerSection from '../components/BannerSection'
import OurServices from '../components/OurServices'
import OurBestWork from '../components/OurBestWork'
import FooterSection from '../components/FooterSection'

export default {
    components: {
        BannerSection,
        OurServices,
        OurBestWork,
        FooterSection
    }
}
</script>

<style>

</style>