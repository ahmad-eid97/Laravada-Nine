<template>
  <section class="intro home_slider">
    <VueSlickCarousel
      :slidesToShow="1"
      :slidesToScroll="1"
      :arrows="true"
      :fade="true"
      :dots="false"
    >
      <div
        class="item item-1"
        v-for="slide in slides"
        :key="slide.id"
        :style="{ background: `url(${slide.background})` }"
      >
        <div class="overlay"></div>
        <div class="row m-0 justify-content-center align-items-center h-100">
          <div class="content">
            <div class="row m-0 align-items-center">
              <div class="col">
                <h1>
                  {{ slide.title }}
                </h1>
                <p>
                  {{ slide.description }}
                </p>
              </div>
              <div class="col-auto">
                <img class="img-fluid" src="/assets/images/logo2.png" alt="" />
              </div>
            </div>
          </div>
        </div>
      </div>
    </VueSlickCarousel>
  </section>
</template>

<script>
import VueSlickCarousel from "vue-slick-carousel";
import "vue-slick-carousel/dist/vue-slick-carousel.css";
import "vue-slick-carousel/dist/vue-slick-carousel-theme.css";
export default {
  components: { VueSlickCarousel },
  name: "AppHomeSlider",
  props: ["slides"],
};
</script>

<style lang="scss">
.intro {
  margin-top: 80px;
  padding: 0;
}
.intro .item {
  min-height: 600px;
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
  position: relative;
  background-repeat: no-repeat !important;
  background-size: cover !important;
}
.intro .item-1 {
  background-image: url(//the7.io/event-agency/wp-content/uploads/sites/48/2018/06/sl-event-04.jpg);
}
.intro .item-2 {
  background-image: url(//the7.io/event-agency/wp-content/uploads/sites/48/2018/06/sl001.jpg);
}
.intro .item-3 {
  background-image: url(//the7.io/event-agency/wp-content/uploads/sites/48/2018/06/sl-event-08.jpg);
}
.intro .item .overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  z-index: 0;
  background-color: rgba(0, 0, 0, 0.51);
}
.intro .item .row {
  min-height: 500px;
}
.intro .item .content {
  position: relative;
  z-index: 1;
  text-align: center;
}
.intro .item img {
  max-width: 356px;
}
.intro .item .content h1 {
  color: rgb(255, 255, 255);
  font-size: 50px;
  font-weight: 700;
  line-height: 57px;
  text-transform: uppercase;
  text-align: left;
  position: relative;
  padding: 0 0 20px;
}
@include sm {
  .intro .item .content h1 {
    font-size: 30px;
    line-height: 47px;
  }
}
.intro .item .content h1:after {
  width: 100px;
  height: 4px;
  background-color: #e73935;
  position: absolute;
  bottom: 0;
  left: 0;
  content: "";
}

.intro .item .content p {
  color: rgb(255, 255, 255);
  font-size: 21px;
  font-weight: 400;
  height: 56px;
  line-height: 28px;
  position: relative;
  text-align: start;
  padding: 15px 0 0;
  max-width: 700px;
}
.intro .item .content .btn {
  background-color: rgb(117, 179, 37);
  border-radius: 3px;
  border: none;
  color: rgb(255, 255, 255);
  cursor: pointer;
  font-size: 20px;
  font-weight: 700;
  height: 50px;
  line-height: 20px;
  padding-bottom: 15px;
  padding-left: 35px;
  padding-right: 35px;
  padding-top: 15px;
}
.intro .content .btn:hover {
  color: rgb(117, 179, 37);
  background-color: rgb(255, 255, 255);
}
.intro .slick-prev {
  right: 100px;
  left: auto;
  top: 90%;
}
.intro .slick-next {
  right: 25px !important;
  top: 90%;
}
.intro .slick-prev,
.intro .slick-next {
  width: 40px;
  height: 40px;
  z-index: 2;
}
.intro .slick-prev::before,
.intro .slick-next::before {
  font-family: "slick";
  font-size: 30px;
  line-height: 1;
  opacity: 0.75;
  color: #fff;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
.content {
  text-align: unset !important;
}
</style>
