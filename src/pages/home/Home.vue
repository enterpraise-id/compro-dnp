<script setup lang="ts">
// Import Components
import BannerSlider from "../../components/Slider/SliderV1/SliderV1.vue";
import ProductSlider from "../../components/Slider/ProductSlider.vue";
import ProductList from "./components/ProductList";
import HowToFind from "../../components/HowToFind.vue";
import ArticleCard from "../../components/ArticleCard.vue";
import useGetQueries from "../../composable/useGetQueries";
import { MainBanner } from "../../typings/MainBanner";
import ArticleSection from "./components/ArticleSection.vue";
import {Product} from "../../typings/Product";
import { ImageSource } from "mapbox-gl";
import { ref } from "@vue/reactivity";

// Initial Composable
// const { data: mainBanners } = useGetQueries<MainBanner>('main-banners', {
//   autoFetch: true,
//   perPage: 5
// });
const imagesSlider = ref<any[]>([
  {
    id: 1,
    imageSourceUrl: '/img/BANNER-01.png',
    createdAt: '0'
  },
  {
    id: 2,
    imageSourceUrl: '/img/BANNER-02.png',
    createdAt: '0'
  },
  {
    id: 3,
    imageSourceUrl: '/img/BANNER-03.png',
    createdAt: '0'
  }
])
const { data: featuredProducts } = useGetQueries<Product>('product', {
  autoFetch: true,
  perPage: 5
});
</script>

<template>
  <div id="banner" class="">
    <BannerSlider :items="imagesSlider" />
  </div>

  <div id="product-slider" class="pt-10 md:pt-0">
    <ProductSlider :items="featuredProducts" />
  </div>
  <div id="product-list" class="mt-20 text-baseColor">
    <ProductList />
  </div>
  <div id="how-to-find" class="mt-20">
    <HowToFind />
  </div>

  <ArticleSection />
</template>
