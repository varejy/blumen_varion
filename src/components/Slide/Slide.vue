<template>
  <div v-if="slide.type === 'Image'" class="group2 parallax__group">
    <div  :style="{ background: slideImage}" class="parallax__layer parallax__layer_slide--back sectionImage parallaxImage bg"></div>
  </div>
  <section v-else>
  <div class="container-fluid sectionSlide">
        <div class="container">
            <div class="row">
                <div class="titleWrapp textWrapp" style="visibility: visible;">
                    <h1 class="sectionTitle">{{slide.title}}</h1>
                </div>
                <div class="subTitleWrapp textWrapp" style="visibility: visible;">
                    <h3 class="subTitle">{{slide.subTitle}}</h3>
                </div>
            </div>
            <Carousel v-bind:slides="slide.images"/>
            <div class="textWrapp text" style="visibility: visible;">
                <p>{{slide.text}}</p>
            </div>
            <div v-if="slide.videoUrl" style="width: 100%; display: flex; justify-content: center;">
              <iframe width="500px" height="281px" v-bind:src="slide.videoUrl" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
            </div>
        </div>
    </div>
  </section>
</template>

<script>
import Carousel from '@/components/Carousel/Carousel';

export default {
  name: "Slide",
  props: ["slide"],
  data() {
    return {
      slideImage: `url(${this.slide.url}) no-repeat center`,
    };
  },
  components: {
    Carousel
  }
};
</script>

<style scoped>
@import url("./Slide.css");
.bg::after {
  background-position: center;
  background-size: cover;
}

</style>
