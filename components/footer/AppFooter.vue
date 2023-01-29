<template>
  <footer>
    <subscribe />
    <div class="copyrights">
      <img
        :src="
          $store.state.websiteSettings.find((one) => one.key === 'logo')
            .plain_value
        "
        alt="logoImage"
        style="width: 200px !important"
      />
      <ul class="footerLinks">
        <li v-for="page in $store.state.footerPages" :key="page.id">
          <b-nav-item
            :to="localePath(generatePagePath(page.id))"
            v-if="page.status"
            >{{ page.name }}</b-nav-item
          >
        </li>
      </ul>
      <p>© Powered By: Rail Coder 2022-2023. All rights reserved.</p>
    </div>
  </footer>
</template>

<script>
import Subscribe from "../subscribe/subscribe.vue";

export default {
  name: "AppFooter",
  components: { Subscribe },
  data() {
    return {};
  },
  beforeMount() {},
  methods: {
    generatePagePath(id) {
      switch (id) {
        case 1:
          return "/about";
        case 2:
          return "/contact";
        case 3:
          return "/terms";
        case 4:
          return "/policy";
      }
    },
  },
};
</script>
<style lang="scss">
footer {
  background-color: #20262a;
}
.footerLinks {
  list-style: none;
  li {
    color: #fff;
    a.nuxt-link-active {
      color: var(--main-color);
    }
  }
}
footer .copyrights {
  padding: 20px 65px;
  text-align: center;
}
footer .copyrights p {
  color: rgb(255, 255, 255);
  font-size: 13px;
  font-weight: 400;
  line-height: 18.2px;
  text-align: center;
  margin: 15px 0 0;
}
footer h5 {
  color: rgb(255, 255, 255);
  font-size: 15px;
  line-height: 19.5px;
  margin-bottom: 20px;
}
footer h6 {
  color: rgb(255, 255, 255);
  font-size: 14px;
  line-height: 21px;
  margin-bottom: 5px;
  font-size: 14px;
  line-height: 21px;
  margin-bottom: 5px;
}
footer p {
  color: rgb(133, 134, 140);
  font-size: 14px;
  line-height: 21px;
}
footer .widgets a {
  background-color: rgba(133, 134, 140, 0.15);
  border-radius: 50%;
  color: rgb(133, 134, 140);
  font-size: 14px;
  height: 26px;
  line-height: 26px;
  margin-bottom: 2px;
  margin-left: 2px;
  margin-right: 2px;
  margin-top: 2px;
  position: relative;
  text-align: center;
  width: 26px;
  display: inline-block;
}
</style>
