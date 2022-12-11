<template>
  <section class="news">
    <div class="row m-0">
      <div class="col-lg-6 p-0" v-if="blogs.length >= 1">
        <h3>NEWS & EVENTS</h3>
        <div
          v-for="blog in blogs.slice(0, 3)"
          :key="blog.id"
          class="row item mx-0"
        >
          <div class="col-auto">
            <img :src="blog.image" width="83" height="83" :alt="blog.title" />
          </div>
          <div class="col">
            <h4>
              <a href="#">
                {{ blog.title }}
              </a>
            </h4>
            <p>
              {{ blog.short_description }}
            </p>
            <nuxt-link :to="`/blog/${blog.id}`" class="btn">
              Read more
            </nuxt-link>
          </div>
        </div>
      </div>
      <div class="col-lg-6">
        <h3>OUR GALLERY FEED</h3>
        <div class="row m-0">
          <CoolLightBox :items="items" :index="index" @close="index = null">
          </CoolLightBox>
          <div class="images-wrapper p-0">
            <div
              class="row justify-content-between m-0"
              v-if="items.length >= 1"
            >
              <div
                class="col-auto p-0"
                v-for="(image, imageIndex) in items"
                :key="imageIndex"
                @click="index = imageIndex"
              >
                <div
                  class="image"
                  :style="{ backgroundImage: 'url(' + image + ')' }"
                >
                  <div class="rollover">
                    <div class="rollover-content">
                      <a class="rollover-link" href="#">
                        <i class="fa-solid fa-magnifying-glass-plus"></i>
                      </a>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "AppHomeNews",
  props: ["blogs"],
  data() {
    return {
      items: [
        "https://the7.io/event-agency/wp-content/uploads/sites/48/2018/06/sl-event-02-383x383.jpg",
        "https://the7.io/event-agency/wp-content/uploads/sites/48/2018/06/sl-event-23-383x383.jpg",
        "https://the7.io/event-agency/wp-content/uploads/sites/48/2018/06/sl-event-11-383x383.jpg",
        "https://the7.io/event-agency/wp-content/uploads/sites/48/2018/06/sl-event-04-383x383.jpg",
        "https://the7.io/event-agency/wp-content/uploads/sites/48/2018/06/sl-event-07-383x383.jpg",
        "https://the7.io/event-agency/wp-content/uploads/sites/48/2018/06/sl-event-01-383x383.jpg",
        "https://the7.io/event-agency/wp-content/uploads/sites/48/2018/06/sl-event-25-383x383.jpg",
        "https://the7.io/event-agency/wp-content/uploads/sites/48/2018/06/sl-event-08-383x383.jpg",
        "https://the7.io/event-agency/wp-content/uploads/sites/48/2018/06/sl-event-06-383x383.jpg",
        "https://the7.io/event-agency/wp-content/uploads/sites/48/2018/06/sl001-383x383.jpg",
        "https://the7.io/event-agency/wp-content/uploads/sites/48/2018/06/sl-event-05-383x383.jpg",
        "https://the7.io/event-agency/wp-content/uploads/sites/48/2018/06/sl-event-28-383x383.jpg",
      ],
      index: null,
    };
  },
};
</script>

<style lang="scss">
.news {
  padding: 80px 50px 70px;
}
@include sm {
  .news {
    padding: 40px 10px;
  }
}
.news .item {
  margin-top: 30px;
}
.news h3 {
  color: rgb(36, 46, 53);
  font-size: 26px;
  line-height: 36px;
  text-align: center;
  margin-bottom: 80px;
  padding-bottom: 15px;
  position: relative;
  z-index: 1;
}
.news h3:after {
  width: 100px;
  height: 4px;
  background-color: #e73935;
  position: absolute;
  bottom: 0;
  left: calc(50% - 50px);
  content: "";
  z-index: 1;
}
.news h4 a {
  color: rgb(36, 46, 53);
  font-size: 22px;
  line-height: 32px;
  text-decoration-color: rgb(36, 46, 53);
  text-decoration-line: none;
  text-decoration-style: solid;
  transition-delay: 0s;
  transition-duration: 0.35s;
  transition-property: color;
  transition-timing-function: ease;
}
.news h4 a:hover {
  color: rgb(234, 54, 46);
}
.news p {
  color: rgb(113, 120, 124);
  font-size: 16px;
  line-height: 28px;
  margin-bottom: 10px;
}
.news .btn {
  border: none;
  padding: 0;
  color: rgb(36, 46, 53);
  font-size: 12px;
  font-weight: 700;
  line-height: 16px;
  padding-bottom: 8px;
  position: relative;
}
.news .btn:after {
  height: 2px;
  background-color: #e73935;
  position: absolute;
  bottom: 0;
  left: 0;
  right: 100%;
  content: "";
  z-index: 1;
  transition: all 0.3s linear;
}
.news .btn:hover:after {
  height: 2px;
  background-color: #e73935;
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  content: "";
  z-index: 1;
}
.news .image {
  height: 140px;
  width: 140px;
  background-size: cover;
  position: relative;
  margin-bottom: 2px;
}

.news .image .rollover {
  transform: scaleY(0);
  background-color: rgba(231, 56, 53, 0.5);
  opacity: 0;
  display: flex;
  display: flex;
  align-items: center;
  justify-content: space-around;
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 100%;
  line-height: normal;
  text-align: center;
  transition: all 0.3s ease-in-out;
  -webkit-transform-style: preserve-3d;
}
.news .image:hover .rollover {
  transform: scaleY(1);
  opacity: 1;
}
.news .image .rollover-content {
  padding: 10px;
  width: 90%;
  box-sizing: border-box;
  line-height: normal;
  text-align: center;
}

.news .image .rollover-content .rollover-link {
  color: rgb(255, 255, 255);
  font-size: 30px;
}
.news .image .rollover-content h4 a {
  font-size: 18px;
  line-height: 1.52;
  color: rgb(255, 255, 255);
  text-decoration: none;
}
.news .image .rollover-content p a {
  font-size: 12px;
  line-height: 1.52;
  color: rgb(255, 255, 255);
  text-decoration: none;
}
@include xs {
  .item {
    display: block;
  }
}
</style>
