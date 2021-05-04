<template>
  <div class="carousel" ref="carousel">
    <div ref="container" class="sliderContainer sliderTrack">
      <div v-if="slides" class="sliderTrack" ref="sliderTrack">
        <div
          v-for="slide of slides"
          :slide="slide"
          :key="slide.id"
          class="slide"
        >
          <div class="imageWrapper">
            <img class="image" @click="onOpenSlider(slide)"  draggable="false" v-bind:src="slide.url" />
          </div>
        </div>
      </div>
    </div>
    <div v-if="windowWidth < 577" class="dotsPagination">
      <div
        v-for="slide of slides.slice(slides.length / 2)"
        :slide="slide"
        :key="slide.id"
        class="dot"
      ><span></span></div>
    </div>  
  </div>
</template>

<script>
import dataBase from "@/dataBase";
const TIME_TO_NEXT_SWITCHING = 4000;
const SWITCHING_DURATION = 800;

export default {
  name: "Carousel",
  /* eslint-disable */ props: ["slides"],
  data() {
    return {
      animation: false,
      windowWidth: window.innerWidth,
      slideWidth: (window.innerWidth < 577 ? window.innerWidth / 2 - 30 : window.innerWidth < 768 ? 120 : window.innerWidth < 992 ? 165 : window.innerWidth >= 1200 ? 210 : 176) + 20,
      maxSlideIndex: this.slides && this.slides.length - 1,
      activeSlide: dataBase.datas.activeSlide,
      activeSlides: dataBase.datas.activeSlides
    };
  },
  mounted() {
    let slides = document.querySelectorAll(".slide");
    slides.forEach((item) => {
      item.style.width = this.slideWidth - 20 + "px";
    });

    if (this.windowWidth < 577) {
      let dots = document.querySelectorAll('.dot');

      dots[0].classList.add('active');

      setInterval(() => {
        console.log(dots)
        dots[0].classList.remove('active');
        dots.forEach((dot, i) => {
          let index = i !== 0 ? i-- : dots.length;
          i !== 0 && dots[index].classList.remove('active')
          console.log(index)
          dots[index].classList.add('active')
        })
      }, 2000)
    }

    this.slides &&
      setTimeout(() => {
        this.setTimeoutToNextSlide();
        this.sliderTrack = this.$refs.sliderTrack;
        this.container = this.$refs.container;
        this.sliderTrack2 = this.sliderTrack.cloneNode(true);

        this.container.appendChild(this.sliderTrack2);
      }, 2000);
  },
  beforeUpdate() {
    this.isUnmount = true;
  },
  methods: {
    setTimeoutToNextSlide() {
      this.sliderTimoutId = setTimeout(() => {
        if (this.isUnmount) {
          return;
        }
        this.doSlideSwitch();
      }, TIME_TO_NEXT_SWITCHING);
    },

    onOpenSlider(slide) {
      dataBase.setActiveSlides(slide, this.slides)
    },

    doSlideSwitch() {
      this.animation = true;
      this.sliderTrack.style.transition = `left ${SWITCHING_DURATION}ms`;
      this.sliderTrack2.style.transition = `left ${SWITCHING_DURATION}ms`;
      let position = +this.sliderTrack.style.left.replace(/[-|px]/g, "");
      let position2 = +this.sliderTrack2.style.left.replace(/[-|px]/g, "");
      let widthCarousel = this.slideWidth * this.sliderTrack.childNodes.length;

      this.sliderTrack.id = "sliderTrack1";
      this.sliderTrack2.id = "sliderTrack2";

      if (this.sliderTrack.style.left.indexOf("-") === 0 && position >= widthCarousel) {
        this.sliderTrack.style.transition = `left 0ms`;
        this.sliderTrack.style.left = `${widthCarousel / 2 + this.slideWidth * 2}px`;
      } else if (this.sliderTrack2.style.left.indexOf("-") === 0 && position2 >= widthCarousel * 2) {
        this.sliderTrack2.style.transition = `left 0ms`;
        this.sliderTrack2.style.left = `-${widthCarousel / 2 - this.slideWidth * 2}px`;
      } else {
        this.sliderTrack2.style.left = this.sliderTrack2.style.left.indexOf("-") === 0? `-${position2 + this.slideWidth}px` : `${position2 - this.slideWidth}px`;
        this.sliderTrack.style.left = this.sliderTrack.style.left.indexOf("-") === 0 ? `-${position + this.slideWidth}px` : `${position - this.slideWidth}px`;
      }
      this.sliderTimoutId = setTimeout(() => {
        this.animation = false;
        this.setTimeoutToNextSlide();
      }, SWITCHING_DURATION);
    },
  }
};
</script>

<style scoped>
@import url("./Carousel.css");

.dotsPagination {
  margin-top: 10px;
  text-align: center;
  display: flex;
  justify-content: center;
}

.dot {
  width: 10px;
  height: 10px;
  margin: 5px 7px;
  background: #d6d6d6;
  display: block;
  -webkit-backface-visibility: visible;
  transition: opacity 0.2s ease;
  border-radius: 30px;
  cursor: pointer;
}

.active {
  background: #869791;
}

.testmove {
  display: block;
  position: absolute;
  top: 0;
  height: 150px;
  width: 150px;
  margin: 200px;
  background: #333;
  color: white;
}

@media (max-width: 992px) {
  .image {
    height: 150px;
    object-fit: cover;
  }
}
</style>
