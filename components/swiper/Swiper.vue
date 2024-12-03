<script setup>
// Swiper JS 核心功能
import Swiper from "swiper";
// Swiper 核心與模組的樣式
import "swiper/css";
import "swiper/css/navigation";
import "swiper/css/pagination";

// 使用 defineProps() 設定以下 props 接受來自父元件的參數
const props = defineProps({
  autoplay: Object,
  pagination: Object,
  navigation: Object,
  loop: Boolean,
  slidesPerView: Number,
  modules: Array,
  breakpoints: Object,
});

// 取得輪播容器的 DOM 節點
const swiperRef = ref(null);
// 在 onMounted() 生命週期把 DOM 節點與元件的 props 傳入 new Swiper()
onMounted(() => {
  new Swiper(swiperRef.value, props);
});
</script>

<template>
  <div class="swiper" ref="swiperRef">
    <div class="swiper-wrapper">
      <slot />
    </div>
    <div class="swiper-pagination"></div>

    <div class="swiper-button-next"></div>
    <div class="swiper-button-prev"></div>
  </div>
</template>

<style scoped></style>
