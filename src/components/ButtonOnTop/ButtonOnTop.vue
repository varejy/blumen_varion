<template>
  <div class="button" @click="onTop" ref="btn" title="Go to top">
    <img v-bind:src="image" alt="" />
  </div>
</template>

<script>
import dataBase from "@/dataBase";

export default {
  name: "ButtonOnTop",
  props: ["scrolling"],
  data() {
    return {
      image: dataBase.datas.buttonOnTop.image,
    };
  },
  mounted() {
    this.btn = this.$refs.btn;
  },
  beforeUpdate() {
    this.scrollFunction();
  },
  methods: {
    scrollFunction() {
      if (this.scrolling > 901) {
        this.btn.style.display = "flex";
      } else {
        this.btn.style.display = "none";
      }
    },
    onTop() {
      this.$emit("change-scroll-position", true);
    },
  },
};
</script>

<style scoped>
.button {
  display: none;
  align-items: center;
  justify-content: center;
  position: fixed;
  bottom: 20px;
  right: 30px;
  z-index: 99;
  cursor: pointer;
  padding: 5px;
  border-radius: 2px;
  width: 32px;
  height: 32px;
  box-sizing: border-box;
  border: 1px solid #c0c0c0;
}

img {
  vertical-align: middle;
  border-style: none;
  height: 14px;
  width: 9px;
}
</style>
