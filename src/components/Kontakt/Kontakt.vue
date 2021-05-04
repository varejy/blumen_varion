<template>
  <div class="container-fluid sectionSlide">
    <div class="container" ref="container">
      <div class="row" id="headContainer">
        <div class="titleWrapp textWrapp">
          <h1 class="sectionTitle">{{ data.title }}</h1>
        </div>
        <div class="subTitleWrapp textWrapp">
          <h3 class="subTitle">{{ data.subTitle }}</h3>
        </div>
        <div class="titleWrapp textWrapp">
          <img v-bind:src="data.image" style="float: left" alt="image" />
        </div>
      </div>
      <div class="textWrapp text">
        <p class="storngText">{{ data.strongText }}</p>
        <p>{{ data.text }}</p>
        <p>Tel: {{ data.tel }}</p>
        <p>Fax: {{ data.fax }}</p>
        <p>
          E-Mail: <a class="mail" v-bind:href="data.email">{{ data.email }}</a>
        </p>
      </div>
      <div id="map"></div>
    </div>
  </div>
</template>

<script>
import dataBase from "@/dataBase";

export default {
  name: "Kontakt",
  data() {
    return {
      data: dataBase.datas.kontakt,
    };
  },
};
</script>

<style scoped>
@import url("./Kontakt.css");

img {
  height: auto;
  width: 100%;
  object-fit: contain;
  max-width: 369.33px;
}

@media (max-width: 575.99px) {
  h1 {
    font-size: 26px;
  }
}
</style>
