<template>
  <div class="home">
    <app-home-slider :sliderData="sliderData"></app-home-slider>
    <app-home-what></app-home-what>
    <app-home-services :services="services"></app-home-services>
    <app-home-testimonials :testimonials="testimonials"></app-home-testimonials>
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
  },
  async asyncData({ $axios }) {
    const sliderData = await $axios.get('/sliders');

    const services = await $axios.get('/services');

    const testimonials = await $axios.get('/testimonials');

    return {
      sliderData: sliderData.data.data.sliders,
      services: services.data.data.services,
      testimonials: testimonials.data.data.testimonials,
    }
  }
}
</script>
