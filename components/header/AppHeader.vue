<template>
  <header
    :class="!topOfPage ? 'onScroll' : ''"
    class="header header-style-2 clearfix"
  >
    <div class="cart" :class="openCart ? 'opened' : ''">
      <div class="head">
        <i class="fa-regular fa-xmark" @click="openCart = false"></i>
        <button
          @click="goToCheckout"
          :disabled="$store.state.cartItems.length <= 0"
        >
          <i class="fa-regular fa-badge-check"></i> Checkout
        </button>
      </div>
      <cart />
    </div>
    <div class="row m-0 w-100">
      <b-navbar toggleable="lg">
        <b-navbar-brand href="/">
          <img
            src="/assets/images/logo.png"
            alt="logoImage"
            style="maxwidth: 170px"
          />
        </b-navbar-brand>

        <div class="d-flex align-items-center smallScr">
          <lang-switch></lang-switch>
          <div class="m-0 cartIcon" @click="openCart = !openCart">
            <span>{{ $store.state.cartItems.length }}</span>
            <i class="fa-regular fa-cart-plus"></i>
          </div>
          <div v-if="$store.state.user" class="logout" @click="logout">
            <i class="fa-regular fa-right-from-bracket"></i>
          </div>

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
        </div>

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
            <b-nav-item
              :to="localePath('/login')"
              v-if="$store.state.user"
              @click="logout"
              >Logout</b-nav-item
            >
          </b-navbar-nav>
          <div class="d-flex align-items-center quote_area">
            <a href="#" class="btn">
              REQUEST A QUOTE
              <i class="fa-solid fa-angle-right"></i>
            </a>
          </div>
        </b-collapse>
        <div class="d-flex align-items-center largeScr">
          <lang-switch></lang-switch>
          <div class="m-0 cartIcon" @click="openCart = !openCart">
            <span>{{ $store.state.cartItems.length }}</span>
            <i class="fa-regular fa-cart-plus"></i>
          </div>
          <div v-if="$store.state.user" class="logout" @click="logout">
            <i class="fa-regular fa-right-from-bracket"></i>
          </div>
        </div>
      </b-navbar>
    </div>
  </header>
</template>

<script>
import cart from "../cart/cart.vue";
import langSwitch from "../langSwitch/langSwitch.vue";
export default {
  name: "AppHeader",
  data() {
    return {
      topOfPage: true,
      openCart: false,
    };
  },
  components: {
    langSwitch,
    cart,
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
    goToCheckout() {
      this.openCart = false;
      this.$router.push("/checkout");
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
  .cart {
    width: 390px;
    height: 100vh;
    position: fixed;
    top: 0;
    right: 0;
    transform: translateX(390px);
    background-color: #fff;
    z-index: 999999;
    box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.2);
    .head {
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 10px;
      & > i {
        border: 1px solid var(--main-color);
        border-radius: 5px;
        width: 30px;
        height: 30px;
        display: grid;
        place-items: center;
        cursor: pointer;
        background-color: var(--main-color);
        color: #fff;
        &:hover {
          color: var(--main-color);
          background: transparent;
        }
      }
      button {
        padding: 5px 30px;
        font-size: 1.1rem;
        background-color: var(--main-color);
        color: #fff;
        border: 1px solid var(--main-color);
        display: flex;
        align-items: center;
        gap: 5px;
        i {
          font-size: 1.1rem;
        }
        &:disabled {
          opacity: 0.5;
          cursor: not-allowed;
          &:hover {
            background-color: var(--main-color);
            color: #fff;
          }
        }
        &:hover {
          background-color: transparent;
          color: var(--main-color);
        }
      }
    }
    &.opened {
      transform: translateX(0);
    }
    @include xs {
      width: 350px;
    }
  }
  .cartIcon {
    border: 1px solid #fff;
    border-radius: 5px;
    width: 45px;
    height: 45px;
    display: grid;
    place-items: center;
    cursor: pointer;
    position: relative;
    margin: 0 15px !important;
    span {
      position: absolute;
      top: -15px;
      right: -10px;
      width: 30px;
      height: 30px;
      background-color: var(--main-color);
      border-radius: 50%;
      color: #fff;
      display: grid;
      place-content: center;
      font-size: 1.2rem;
      border: 1px solid #fff;
      @include sm {
        font-size: 1rem;
      }
    }
    i {
      color: #fff;
    }
    @include sm {
      width: 40px;
      height: 40px;
      margin: 0 10px !important;
    }
    &:hover {
      background-color: var(--main-color);
      border-color: var(--main-color);
      i {
        color: #fff;
      }
    }
  }
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
  @include md {
    display: none;
  }
}
.smallScr {
  align-items: center;
  display: none !important;
  @include md {
    display: flex !important;
  }
}
.largeScr {
  align-items: center;
  display: flex !important;
  @include md {
    display: none !important;
  }
}
nav {
  padding: 0 60px 0 !important;
  @include md {
    padding: 20px 10px !important;
  }
}
.onScroll nav {
  padding: 0 60px 0 !important;
  @include sm {
    padding: 20px 10px !important;
  }
}
.onScroll nav .nav-item {
  padding: 20px 10px;
}
.navbar-brand {
  width: 180px;
  transition: all 0.3s linear;
  @include sm {
    width: 150px;
  }
}
.navbar-brand img {
  max-width: 100%;
  transition: all 0.3s linear;
}
/* .onScroll .navbar-brand img {
  max-width: 70px;
} */

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
  margin: 0;
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
