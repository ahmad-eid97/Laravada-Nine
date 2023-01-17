<template>
  <div class="home">
    <app-home-slider :slides="slides"></app-home-slider>
    <app-home-what></app-home-what>
    <app-home-services :services="services"></app-home-services>
    <app-home-testimonials :testimonials="testimonials"></app-home-testimonials>
    <app-home-activities :activities="activities" />
    <app-home-steps :steps="steps" />
    <app-home-news :blogs="blogs" :gallery="gallery"></app-home-news>
  </div>
</template>

<script>
import AppHomeNews from "../components/home/AppHomeNews.vue";
import AppHomeServices from "../components/home/AppHomeServices.vue";
import AppHomeSlider from "../components/home/AppHomeSlider.vue";
import AppHomeTestimonials from "../components/home/AppHomeTestimonials.vue";
import AppHomeWhat from "../components/home/AppHomeWhat.vue";
import AppHomeActivities from "../components/home/AppHomeActivities.vue";
import AppHomeSteps from "../components/home/AppHomeSteps.vue";

export default {
  name: "Home",
  components: {
    AppHomeSlider,
    AppHomeWhat,
    AppHomeServices,
    AppHomeTestimonials,
    AppHomeNews,
    AppHomeActivities,
    AppHomeSteps,
  },
  async asyncData({ $axios, app }) {
    const slides = await $axios.get("/sliders", {
      headers: {
        "Accept-Language": app.i18n.locale,
      },
    });

    const services = await $axios.get("/services");

    const blogs = await $axios.get("/blogs?latest=1");

    const testimonials = await $axios.get("/testimonials");

    const galleries = await $axios.get("/galleries");

    const activities = await $axios.get("/sections/activities", {
      headers: {
        "Accept-Language": app.i18n.locale,
      },
    });

    const steps = await $axios.get("/sections/steps", {
      headers: {
        "Accept-Language": app.i18n.locale,
      },
    });

    return {
      slides: slides.data.data.sliders,
      services: services.data.data.services,
      blogs: blogs.data.data.blogs,
      testimonials: testimonials.data.data.testimonials,
      gallery: galleries.data.data.galleries,
      activities: activities.data.data,
      steps: steps.data.data,
    };
  },
};
</script>
