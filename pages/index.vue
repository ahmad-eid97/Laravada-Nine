<template>
  <div class="home">
    <app-home-slider></app-home-slider>
    <app-home-what></app-home-what>
    <app-home-services></app-home-services>
    <app-home-testimonials></app-home-testimonials>
    <app-home-news></app-home-news>
  </div>
</template>

<script>
import AppHomeNews from '../components/home/AppHomeNews.vue'
import AppHomeServices from '../components/home/AppHomeServices.vue'
import AppHomeSlider from '../components/home/AppHomeSlider.vue'
import AppHomeTestimonials from '../components/home/AppHomeTestimonials.vue'
import AppHomeWhat from '../components/home/AppHomeWhat.vue'

export default {
  name: 'Home',
  components: {
    AppHomeSlider,
    AppHomeWhat,
    AppHomeServices,
    AppHomeTestimonials,
    AppHomeNews
    
    
  }
}
</script>
