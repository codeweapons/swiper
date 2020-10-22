<template>
  <div>
    <div class="examples">
      <div class="bannerBox">
        <div class="swiper-container">
          <div class="swiper-wrapper">
            <div
              class="swiper-slide"
              v-for="(item, index) in banner"
              :key="index"
            >
              <img :src="item.picture_path" alt="" />
            </div>
          </div>
          <div class="swiper-button-prev"></div>
          <div class="swiper-button-next"></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Swiper from "swiper";
import "swiper/dist/css/swiper.min.css";
export default {
  data() {
    return {
      bannerIndex: 0,
      bannerTxt: "手写的处方",
      banner: [
        {
          picture_txt: "手写的处方",
          picture_path: require("../img/t1.png"),
        },
        {
          picture_txt: "机打的处方",
          picture_path: require("../img/t2.png"),
        },
        {
          picture_txt: "机打的处方",
          picture_path: require("../img/t3.png"),
        },
        {
          picture_txt: "机打的处方",
          picture_path: require("../img/t4.png"),
        },
      ],
    };
  },
  mounted() {
    let that = this;
    /* eslint-disable */
    let mySwiper = new Swiper(".swiper-container", {
      direction: "horizontal", //滑动方向，可设置水平(horizontal)或垂直(vertical)。
      loop: true, // 设置为true 则开启loop模式
      autoplay: false, // 自动切换时间
      slidesPerView: "auto", // 设置slider容器能够同时显示的slides数量(carousel模式)。类型：number or auto
      centeredSlides: true, // 设定为true时，active slide会居中，而不是默认状态下的居左。
      spaceBetween: 10, // 在slide之间设置距离（单位px）。
      loopAdditionaSlider: 0, // loop模式下会在slides前后复制若干个slide,，前后复制的个数不会大于原总个数。
      navigation: {
        nextEl: ".swiper-button-next",
        prevEl: ".swiper-button-prev",
      },
    });
  },
};
</script>

<style lang="scss" scoped>
.examples {
  position: absolute;
  left: 500px;
  width: 1000px;
  overflow: hidden;
  background-color: #f5f0f0;
  font-size: 14px;
}
.bannerBox {
  position: relative;
  height: 380px;
}
.swiper-container {
  width: 100%;
  height: 100%;
}
.swiper-container .swiper-wrapper .swiper-slide {
  width: 80% !important;
  overflow: hidden;
  display: flex;
  align-items: center;
}
.swiper-container .swiper-wrapper .swiper-slide img {
  position: relative;
  left: 50px;
  width: 80%;
  height: 300px;
  border-radius: 5px;
}
.swiper-container .swiper-wrapper .swiper-slide-prev,
.swiper-container .swiper-wrapper .swiper-slide-next {
  height: 260px !important;
  margin-top: 60px;
}
.swiper-container .swiper-wrapper .swiper-slide-next {
  position: relative;
  left: -100px;
}
.swiper-container .swiper-wrapper .swiper-slide-prev img,
.swiper-container .swiper-wrapper .swiper-slide-next img {
  width: 100%;
  height: 100%;
}
</style>
