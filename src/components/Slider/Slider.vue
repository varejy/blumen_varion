<template>
  <div class="sliderWrapp active">
    <div class="slider">
      <div class="play active">
        <img
          src="http://blumen.varion.net/wp-content/themes/carpe-diem/img/play-circle-regular.svg"
          alt=""
        />
      </div>
      <div class="pause">
        <img
          src="http://blumen.varion.net/wp-content/themes/carpe-diem/img/pause-circle-regular.svg"
          alt=""
        />
      </div>
      <div class="close-modal">
        <img
          src="http://blumen.varion.net/wp-content/themes/carpe-diem/img/times-solid.svg"
          alt=""
        />
      </div>
      <div class="slider__window">
        <div class="main-slide">
          <img
            class="some-img active"
            src="http://blumen.varion.net/wp-content/uploads/2020/11/https___www.blumen-ambiente.eu_wp-content_uploads_2020_11_Haarkranz.jpg"
            alt=""
          /><img
            class="some-img"
            src="http://blumen.varion.net/wp-content/uploads/2020/11/https___www.blumen-ambiente.eu_wp-content_uploads_2020_11_flowers-5093757_1280.jpg"
            alt=""
          /><img
            class="some-img"
            src="http://blumen.varion.net/wp-content/uploads/2020/11/flower-3185225_1280.jpg"
            alt=""
          /><img
            class="some-img"
            src="http://blumen.varion.net/wp-content/uploads/2020/11/https___www.blumen-ambiente.eu_wp-content_uploads_2020_11_wedding-5631610_1280.jpg"
            alt=""
          /><img
            class="some-img"
            src="http://blumen.varion.net/wp-content/uploads/2020/11/https___www.blumen-ambiente.eu_wp-content_uploads_2016_05_Carpe-Diem-Hochzeit-0043.jpg"
            alt=""
          /><img
            class="some-img"
            src="http://blumen.varion.net/wp-content/uploads/2020/11/https___www.blumen-ambiente.eu_wp-content_uploads_2016_05_Carpe-Diem-Hochzeit-0190.jpg"
            alt=""
          /><img
            class="some-img"
            src="http://blumen.varion.net/wp-content/uploads/2020/11/https___www.blumen-ambiente.eu_wp-content_uploads_2016_05_Carpe-Diem-Hochzeit-0196.jpg"
            alt=""
          /><img
            class="some-img"
            src="http://blumen.varion.net/wp-content/uploads/2020/11/https___www.blumen-ambiente.eu_wp-content_uploads_2016_05_Carpe-Diem-Hochzeit-0243.jpg"
            alt=""
          /><img
            class="some-img"
            src="http://blumen.varion.net/wp-content/uploads/2020/11/https___www.blumen-ambiente.eu_wp-content_uploads_2016_05_Carpe-Diem-Hochzeit-0244.jpg"
            alt=""
          /><img
            class="some-img"
            src="http://blumen.varion.net/wp-content/uploads/2020/11/https___www.blumen-ambiente.eu_wp-content_uploads_2016_05_Carpe-Diem-Hochzeit-0301.jpg"
            alt=""
          />
        </div>
      </div>
      <div class="slider__all">
        <img
          class="some-img active"
          src="http://blumen.varion.net/wp-content/uploads/2020/11/https___www.blumen-ambiente.eu_wp-content_uploads_2020_11_Haarkranz.jpg"
          alt=""
        /><img
          class="some-img"
          src="http://blumen.varion.net/wp-content/uploads/2020/11/https___www.blumen-ambiente.eu_wp-content_uploads_2020_11_flowers-5093757_1280.jpg"
          alt=""
        /><img
          class="some-img"
          src="http://blumen.varion.net/wp-content/uploads/2020/11/flower-3185225_1280.jpg"
          alt=""
        /><img
          class="some-img"
          src="http://blumen.varion.net/wp-content/uploads/2020/11/https___www.blumen-ambiente.eu_wp-content_uploads_2020_11_wedding-5631610_1280.jpg"
          alt=""
        /><img
          class="some-img"
          src="http://blumen.varion.net/wp-content/uploads/2020/11/https___www.blumen-ambiente.eu_wp-content_uploads_2016_05_Carpe-Diem-Hochzeit-0043.jpg"
          alt=""
        /><img
          class="some-img"
          src="http://blumen.varion.net/wp-content/uploads/2020/11/https___www.blumen-ambiente.eu_wp-content_uploads_2016_05_Carpe-Diem-Hochzeit-0190.jpg"
          alt=""
        /><img
          class="some-img"
          src="http://blumen.varion.net/wp-content/uploads/2020/11/https___www.blumen-ambiente.eu_wp-content_uploads_2016_05_Carpe-Diem-Hochzeit-0196.jpg"
          alt=""
        /><img
          class="some-img"
          src="http://blumen.varion.net/wp-content/uploads/2020/11/https___www.blumen-ambiente.eu_wp-content_uploads_2016_05_Carpe-Diem-Hochzeit-0243.jpg"
          alt=""
        /><img
          class="some-img"
          src="http://blumen.varion.net/wp-content/uploads/2020/11/https___www.blumen-ambiente.eu_wp-content_uploads_2016_05_Carpe-Diem-Hochzeit-0244.jpg"
          alt=""
        /><img
          class="some-img"
          src="http://blumen.varion.net/wp-content/uploads/2020/11/https___www.blumen-ambiente.eu_wp-content_uploads_2016_05_Carpe-Diem-Hochzeit-0301.jpg"
          alt=""
        />
      </div>
      <div class="modal-right" id="modal-right">
        <img
          src="http://blumen.varion.net/wp-content/themes/carpe-diem/img/chevron-right.svg"
          alt=""
        />
      </div>
      <div class="modal-left" id="modal-left">
        <img
          src="http://blumen.varion.net/wp-content/themes/carpe-diem/img/chevron-left.svg"
          alt=""
        />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Slider",
  props: ['slides', 'activeSlide'],
  mounted() {
      console.log(this.slides, this.activeSlide)
  }
};
</script>

<style scoped>
.sliderWrapp.active {
  display: block;
  position: fixed;
  top: 0;
  left: 0;
  transform: translateY(0);
  z-index: 150;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.9);
  transition-duration: 1.5s;
}

.sliderWrapp {
  transform: translateY(-150%);
  transition-duration: 1.5s;
}

.slider {
  position: relative;
  width: 100%;
  height: 100%;
}

.sliderWrapp.active .play.active, .sliderWrapp.active .close-modal {
    display: block;
}

.play.active {
    display: none;
}

.play {
    display: none;
    position: absolute;
    top: 20px;
    left: 20px;
    cursor: pointer;
}

.pause {
    display: none;
    position: absolute;
    top: 20px;
    left: 20px;
    cursor: pointer;
}

.close-modal {
    display: none;
    position: absolute;
    top: 20px;
    right: 20px;
    cursor: pointer;
}

.slider__window {
    position: absolute;
    top: 45%;
    left: 50%;
    transform: translate(-50%, -50%);
}

.main-slide > .active {
    display: block !important;
    transition-duration: 1s !important;
}

.slider__all {
    position: absolute;
    bottom: 0;
    left: 50%;
    transform: translateX(-50%);
    display: flex;
}

.slider__all > .active {
    border: 2px solid white;
}

.slider__all img {
    width: 60px;
    height: 60px;
    margin: 0;
}

.modal-right {
    display: none;
    justify-content: center;
    align-items: center;
    cursor: pointer;
    position: absolute;
    right: 0;
    top: 50%;
    transform: translateY(-50%);
    width: 38px;
    height: 145px;
    background-color: #000000;
}

.sliderWrapp.active .modal-left, .sliderWrapp.active .modal-right {
    display: flex;
}

.modal-left img, .modal-right img, .play img, .pause img, .close-modal img {
    width: 20px;
    height: 20px;
}

img {
    vertical-align: middle;
    border-style: none;
}

.modal-left {
    display: none;
    justify-content: center;
    align-items: center;
    cursor: pointer;
    position: absolute;
    left: 0;
    top: 50%;
    transform: translateY(-50%);
    width: 38px;
    height: 145px;
    background-color: #000000;
}

.sliderWrapp.active .modal-left, .sliderWrapp.active .modal-right {
    display: flex;
}

.main-slide {
    max-width: 543px;
    max-height: 543px;
}

.main-slide > .some-img {
    display: none;
    transition-duration: 1s;
    object-fit: cover;
    width: 100%;
    height: 100%;
}
</style>
