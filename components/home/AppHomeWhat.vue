<template>
  <section class="what">
    <div class="row m-0 justify-content-center">
      <h2>
        We provide planning experience that orci nisl, facilisis id magna nec,
        maximus vestibulum justo. Quisque malesuada, urna id maximus commodo.
      </h2>
    </div>
    <div class="row m-0 align-items-start">
      <div class="col-sm-6 col-lg-4 item">
        <div class="icon">
          <i class="fa-solid fa-users"></i>
        </div>
        <h4>WHO WE ARE</h4>
        <p>
          Ut orci nisl, facilisis id magna nec, maximus vestibulum justo.
          Quisque malesuada, urna id maximus aliquam, mi tellus commodo mauris,
          vel porta turpis enim elementum, libero id tincidunt ornare, orci quam
          fringilla erat, sed tristique ligula eget augue. Pellentesque habitant
          morbi tristique senectus et netus et malesuada!
        </p>
      </div>
      <div class="col-sm-6 col-lg-4 item">
        <div class="icon">
          <i class="fa-solid fa-sitemap"></i>
        </div>
        <h4>WHAT WE DO</h4>
        <p>
          Quisque elementum, libero id tincidunt ornare, orci quam fringilla
          erat, sed tristique ligula malesuada, urna id maximus aliquam, mi
          tellus commodo mauris, vel porta turpis enim eget augue. Nullam
          pulvinar auctor libero eget gravida. Proin a leo nec nibh fermentum
          congue. Phasellus volutpat vel justo non facilisis.
        </p>
      </div>
      <div class="col-sm-6 col-lg-4 item">
        <div class="icon">
          <i class="fa-solid fa-handshake"></i>
        </div>
        <h4>WHY USE US</h4>
        <p>
          Donec dictum auctor congue. Vivamus vel lorem ipsum – justo et odio
          porttitor laoreet malesuada. Maecenas elementum, libero id tincidunt
          ornare, orci quam fringilla erat, sed tristique varius nec dolor at,
          euismod porttitor sapien. Nullam eu vestibulum nibh. In sit amet
          fringilla lacus, in ornare nibh.
        </p>
      </div>
    </div>
    <div class="row m-0 btns justify-content-center">
      <a href="#" class="btn-right">
        <i class="fa-solid fa-circle-info"></i>
        ABOUT AGENCY
      </a>
      <a href="#" class="btn-left">
        <i class="fa-solid fa-comment-dots"></i>
        CONTACT US
      </a>
    </div>
  </section>
</template>

<script>
export default {
  name: "AppHomeWhat",
};
</script>

<style lang="scss">
.what {
  padding: 80px 50px 70px;
}
@include sm {
  .what {
    padding: 40px 20px;
  }
}
.what h2 {
  color: rgb(36, 46, 53);
  font-size: 40px;
  line-height: 50px;
  text-align: center;
  margin-bottom: 80px;
  max-width: 970px;
}
@include sm {
  .what h2 {
    font-size: 30px;
    line-height: 40px;
  }
}
.what .item {
  text-align: center;
  display: flex;
  justify-content: center;
  flex-direction: column;
  padding: 0 25px 50px;
}
.what .item .icon {
  width: 80px;
  height: 80px;
  line-height: 98px;
  margin: 0 auto 30px;
  background-color: var(--main-color);
}
.what .item .icon i {
  font-size: 38px;
  color: #fff;
}
.what .item h4 {
  color: rgb(36, 46, 53);
  font-size: 26px;
  line-height: 36px;
  padding-bottom: 10px;
  text-align: center;
  position: relative;
}
.what .item h4:after {
  content: "";
  width: 40px;
  height: 3px;
  background-color: var(--main-color);
  position: absolute;
  bottom: 0;
  left: calc(50% - 20px);
}
.what .item p {
  margin-top: 30px;
  color: rgb(113, 120, 124);
  font-size: 16px;
  font-weight: 400;
  line-height: 28px;
  text-align: center;
}
.what .btn-right {
  border: 3px solid rgb(231, 57, 53);
  border-radius: 100px 0 0 100px;
  width: 300px;
  padding: 14px 0;
  text-align: center;
  color: rgb(231, 57, 53);
  text-decoration: none;
  border-right: none;
}
@include xs {
  .what .btn-right {
    border: 3px solid rgb(231, 57, 53);
    border-radius: 100px 0 0 100px;
    width: 300px;
  }
}
.what .btn-left {
  border: 3px solid rgb(231, 57, 53);
  border-radius: 0 100px 100px 0;
  width: 300px;
  padding: 14px 0;
  text-align: center;
  color: rgb(231, 57, 53);
  text-decoration: none;
}

.what .btns {
  position: relative;
  margin-top: 30px;
}
.what .btns::after {
  content: "OR";
  color: #fff;
  background-color: var(--main-color);
  position: absolute;
  font-size: 11px;
  font-weight: 400;
  border-radius: 50%;
  padding: 7px 8px;
  top: calc(50% - 15px);
}
.what .btn-right:hover,
.what .btn-left:hover {
  background-color: var(--main-color);
  color: #fff;
}
</style>
