<template>
  <Header v-bind:scrolling="scrolling"/>
  <Wrapper
    v-bind:scrollIsTop="scrollIsTop"
    @change-scroll-position="data => changeScrollPosition(data)"
    @change-header-width="data => changeHeaderWidth(data)"
  />
  <Slider v-if="activeSlide !== ''"></Slider>
  {{activeSlide}}
  <ButtonOnTop @change-scroll-position="data => changeScrollPosition(data)" v-bind:scrolling="scrolling"/>
</template>

<script>
import Header from "@/components/Header/Header";
import Wrapper from "@/components/Wrapper/Wrapper";
import Slider from '@/components/Slider/Slider';
import ButtonOnTop from '@/components/ButtonOnTop/ButtonOnTop';
import dataBase from "@/dataBase";

export default {
  name: "App",
  data() {
    return {
      scrolling: 0,
      scrollIsTop: false,
      showSlider: false,
      activeSlide: dataBase.datas.activeSlide,
      activeSlides: dataBase.datas.activeSlides
    };
  },
  components: {
    Header,
    Wrapper,
    ButtonOnTop,
    Slider
  },
  methods: {
    changeHeaderWidth(data) {
      this.scrolling = data
    },
    changeScrollPosition(data) {
      this.scrollIsTop = data;
    }
  },
};
</script>

<style>
@import url("./App.css");

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #212529;
}
</style>
