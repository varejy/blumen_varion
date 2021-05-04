<template>
  <div class="parallax" ref="wrapp" @scroll="changeHeaderWidth">
    <div id="group1" class="parallax__group">
      <div class="parallax__layer parallax__layer--base">
        <div class="title-wrapper">
          <div class="title">
            <h1 class="imageSlideTitle h1">
              Blumen sind das Lächeln der Erde.
            </h1>
            <h3 class="imageSlideTitle h3">Ralph Waldo Emerson</h3>
          </div>
        </div>
      </div>
      <div class="parallax__layer parallax__layer--back bg1"></div>
    </div>
    <Liebe v-bind:staticSlide="staticSlide" />
    <Slide v-for="slide of slides" :slide="slide" :key="slide" />
    <Kontakt />
    <Impressum />
    <Datenschutz />
    <Footer />
  </div>
</template>

<script>
import Slide from "@/components/Slide/Slide";
import Kontakt from "@/components/Kontakt/Kontakt";
import Impressum from "@/components/Impressum/Impressum";
import Liebe from "@/components/Liebe/Liebe";
import Datenschutz from "@/components/Datenschutz/Datenschutz";
import Footer from "@/components/Footer/Footer";
import dataBase from "@/dataBase";

export default {
  name: "Wrapper",
  props: ["scrollIsTop"],
  data() {
    return {
      staticSlide: dataBase.datas.staticSlide,
      slides: dataBase.datas.slides,
      scrollPosition: 0,
    };
  },
  watch: {
    scrollIsTop() {
      if (this.scrollIsTop === true) {
        this.backToTop();
      }
    },
    scrollPosition() {
      if (this.scrollPosition === 0 && this.scrollIsTop === true) {
        this.$emit("change-scroll-position", false);
      }
    },
  },
  methods: {
    changeHeaderWidth() {
      const progress = this.$refs.wrapp.scrollTop;
      this.scrollPosition = progress;
      this.$emit("change-header-width", progress);
    },
    backToTop() {
      if (this.scrollPosition > 0) {
        this.$refs.wrapp.scrollBy(0, -80);
        setTimeout(this.backToTop, 0);
      }
    },
  },
  components: {
    Liebe,
    Slide,
    Kontakt,
    Impressum,
    Datenschutz,
    Footer,
  },
};
</script>

<style scoped>
@import url("./Wrapper.css");

.h1, h1 {
  font-size: 2.5rem;
}

.h3, h3 {
    font-size: 1.75rem;
}

.h1, .h2, .h3, .h4, .h5, .h6, h1, h2, h3, h4, h5, h6 {
  margin-bottom: .5rem;
  font-weight: 500;
  line-height: 1.2;
}

h1, h2, h3, h4, h5, h6 {
  margin-top: 0;
  margin-bottom: .5rem;
}
</style>
