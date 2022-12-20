<template>
  <header
    :class="!topOfPage ? 'onScroll' : ''"
    class="header header-style-2 clearfix"
  >
    <div class="row m-0 w-100">
      <b-navbar toggleable="lg">
        <b-navbar-brand href="/">
          <img
            src="/assets/images/logo.png"
            alt="logoImage"
            style="maxwidth: 170px"
          />
        </b-navbar-brand>

        <b-navbar-toggle target="navbar-toggle-collapse">
          <template #default="{ expanded }">
            <span
              class="menu-trigger"
              :class="expanded ? 'active' : ''"
              id="menu03"
            >
              <p></p>
              <p></p>
              <p></p>
            </span>
          </template>
        </b-navbar-toggle>

        <b-collapse
          id="navbar-toggle-collapse"
          class="ml-auto justify-content-between"
          is-nav
        >
          <b-navbar-nav class="align-items-center">
            <b-nav-item :to="localePath('/')">Home</b-nav-item>
            <b-nav-item :to="localePath('/about')">About</b-nav-item>
            <b-nav-item :to="localePath('/services')">Services</b-nav-item>
            <b-nav-item :to="localePath('/testimonials')"
              >Testimonials</b-nav-item
            >
            <b-nav-item :to="localePath('/blogs')">News</b-nav-item>
            <b-nav-item :to="localePath('/careers')">Career</b-nav-item>
            <b-nav-item :to="localePath('/events')">Events</b-nav-item>
            <b-nav-item :to="localePath('/contact')">Contact</b-nav-item>
          </b-navbar-nav>
          <div class="d-flex align-items-center quote_area">
            <a href="#" class="btn">
              REQUEST A QUOTE
              <i class="fa-solid fa-angle-right"></i>
            </a>
            <lang-switch></lang-switch>
            <div v-if="$store.state.user" class="logout" @click="logout">
              <i class="fa-regular fa-right-from-bracket"></i>
            </div>
          </div>
        </b-collapse>
      </b-navbar>
    </div>
  </header>
</template>

<script>
import langSwitch from "../langSwitch/langSwitch.vue";
export default {
  name: "AppHeader",
  data() {
    return {
      topOfPage: true,
    };
  },
  components: {
    langSwitch,
  },
  beforeMount() {
    window.addEventListener("scroll", this.handleScroll);
  },
  mounted() {},
  methods: {
    logout() {
      this.$store.commit("setUserData", null);
      this.$cookies.remove("cms-auth");
      this.$cookies.remove("cms-user");
      this.$router.push(this.localePath("/login"));
    },
    handleScroll() {
      if (window.pageYOffset > 30) {
        if (this.topOfPage) this.topOfPage = false;
      } else {
        if (!this.topOfPage) this.topOfPage = true;
      }
    },
  },
};
</script>
<style lang="scss">
header {
  top: 0;
  left: 0;
  right: 0;
  z-index: 10;
  background-color: rgb(234, 54, 46);
  position: fixed;
}

.logout {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  background-color: #fff;
  color: var(--main-color);
  display: grid;
  place-items: center;
  font-size: 1.2rem;
  cursor: pointer;
}
nav {
  padding: 0 60px 0 !important;
}
.onScroll nav {
  padding: 0 60px 0 !important;
}
.onScroll nav .nav-item {
  padding: 20px 10px;
}
.navbar-brand {
  width: 180px;
  transition: all 0.3s linear;
}
.navbar-brand img {
  max-width: 100%;
  transition: all 0.3s linear;
}
.onScroll .navbar-brand img {
  max-width: 70px;
}

.navbar .nav-item {
  margin: 0 1px;
  position: relative;
  padding: 34px 10px;
  transition: all 0.3s linear;
}
.navbar .nav-item.active,
.navbar .nav-item:hover {
  background-color: rgba(0, 0, 0, 0.09);
}
.navbar .nav-item .nav-link {
  color: rgb(255, 255, 255);
  font-size: 18px;
  font-weight: 400;
  line-height: 22px;
}

.navbar .btn {
  background-color: rgb(210, 52, 48);
  border-radius: 500px;
  color: rgb(255, 255, 255);
  font-size: 14px;
  font-weight: 500;
  line-height: 18px;
  padding-bottom: 12px;
  padding-left: 22px;
  padding-right: 20px;
  padding-top: 12px;
}
.navbar-toggler {
  border: 1px solid #fff;
  outline: none;
  box-shadow: none !important;
}
.menu-trigger p {
  width: 30px;
  height: 5px;
  background: #fff;
  margin: 0 0 2px;
}
.navbar .btn:hover {
  color: rgb(210, 52, 48);
  background-color: rgb(255, 255, 255);
}
.quote_area i {
  max-width: 15px;
}
@include md {
  .onScroll .navbar-nav {
    transform: translateY(-10px);
  }
  .navbar-nav {
    padding: 20px 0;
    transform: translateY(-10px);
  }
  .navbar-nav li {
    padding: 5px 0 !important;
  }
  .navbar-nav li.nav-item a {
    color: #fff !important;
    padding: 5px 20px;
  }
  .btn {
    display: none;
  }
}
</style>
