<template>
  <div ref='header' class="header" v-bind:class="{ headerSmall: windowWidth <= 992 ? false : scrolling !== 0 }">
    <div class="headerBody">
      <a
        href="http://localhost:8080"
        class="headerLogo"
        v-bind:class="{ linkSmall: windowWidth <= 992 ? false : scrolling !== 0 }"
      >
        <img
          class="logo"
          v-bind:class="{ logoSmall: windowWidth <= 992 ? false : scrolling !== 0 }"
          v-bind:src="logo"
          alt="My CMS"
        />
      </a>
      <div
        class="headerBurger"
        v-bind:class="{ active: burgerStatus }"
        @click="changeBurgerStatus(burgerStatus)"
      >
        <span></span>
      </div>
      <div class="navigation-container" v-bind:class="{ active: burgerStatus }">
        <ul id="navigation" class="menu">
          <NavItem v-for="link of links" :link="link" :key="link" />
        </ul>
      </div>
    </div>
  </div>
</template>

//getBoundingClientRect()

<script>
import dataBase from "@/dataBase";
import NavItem from "@/components/NavItem/NavItem";

export default {
  name: "Header",
  props: ["scrolling"],
  data() {
    return {
      burgerStatus: false,
      windowWidth: window.innerWidth,
      ...dataBase.datas.header,
    };
  },
  mounted() {
    this.header = this.$refs.header;
    if (/Mobi|Android/i.test(navigator.userAgent)) {
      this.header.style.width = '100%'
    } else {
      this.header.style.width = 'calc(100% - 15px)'
    }
    this.windowWidth = window.innerWidth
    
  },
  methods: {
    changeBurgerStatus(burgerStatus) {
      this.burgerStatus = !burgerStatus;
    },
  },
  components: {
    NavItem
  },
};
</script>

<style scoped>
*,
::after,
::before {
  box-sizing: border-box;
}
.header {
  position: fixed;
  /*width: 99.22%;*/
  top: 0;
  left: 0;
  z-index: 10;
  padding: 0 33px 0 33px;
}
.headerSmall {
  height: 56px;
  animation: minHeaderHeight 0.6s linear;
}

.small {
  -moz-transition-duration: 0.7s;
  -o-transition-duration: 0.7s;
  -webkit-transition-duration: 0.7s;
  transition-duration: 0.7s;
}

.linkSmall {
  padding: 18px 18px 18px 0 !important;
}

.header:before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: 2;
  background-color: #000000;
  -moz-transition-duration: 0.5s;
  -o-transition-duration: 0.5s;
  -webkit-transition-duration: 0.5s;
  transition-duration: 0.5s;
}
.headerBody {
  position: relative;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-pack: justify;
  -ms-flex-pack: justify;
  justify-content: flex-start;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
}
.headerLogo {
  -webkit-box-flex: 0;
  -ms-flex: 0 0 100px;
  flex: 0 0 auto;
  position: relative;
  z-index: 3;
  padding: 27px 36px 27px 0;
  min-width: 200px;
}

img {
  vertical-align: middle;
  border-style: none;
}

.logo {
  height: 55px;
  display: block;
  -moz-transition-duration: 0.7s;
  -o-transition-duration: 0.7s;
  -webkit-transition-duration: 0.7s;
  transition-duration: 0.7s;
}

.logoSmall {
  height: 20px !important;
}

.navigation-container {
  width: 65%;
}

.menu {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  justify-content: space-between;
  position: relative;
  z-index: 2;
  width: 730px;
  padding: 0;
  margin: 0 auto;
}

@media (max-width: 1100px) {
  .headerLogo .logo {
    height: 45px;
  }
}

@media (max-width: 1050px) {
  .headerLogo .logo {
    height: 35px;
  }
}

@media (max-width: 992px) {
  .headerLogo {
    -webkit-box-flex: 0;
    -ms-flex: 0 0 75px;
    flex: 0 0 75px;
  }
  .menu {
    display: block;
    margin: 40px 0 0 0;
    padding: 0;
    width: 100%;
  }
  .navigation-container {
    overflow: auto;
    position: fixed;
    top: -100%;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: #000000;
    padding: 70px 0 20px 0;
    -webkit-transition: all 0.8s ease 0s;
    -o-transition: all 0.8s ease 0s;
    transition: all 0.8s ease 0s;
  }
  .headerBurger {
    display: block;
    position: relative;
    margin-left: auto;
    width: 30px;
    height: 20px;
    z-index: 3;
  }
  .headerBurger:before,
  .headerBurger:after {
    content: "";
    background-color: #fff;
    position: absolute;
    width: 100%;
    height: 2px;
    left: 0;
    -webkit-transition: all 0.8s ease 0s;
    -o-transition: all 0.8s ease 0s;
    transition: all 0.8s ease 0s;
  }
  .headerBurger span {
    position: absolute;
    background-color: #fff;
    left: 0;
    width: 100%;
    height: 2px;
    top: 9px;
    -webkit-transition: all 0.8s ease 0s;
    -o-transition: all 0.8s ease 0s;
    transition: all 0.8s ease 0s;
  }
  .headerBurger:before {
    top: 0;
  }
  .headerBurger:after {
    bottom: 0;
  }
  .headerBurger.active:before {
    -webkit-transform: rotate(45deg);
    -ms-transform: rotate(45deg);
    transform: rotate(45deg);
    top: 9px;
  }
  .headerBurger.active:after {
    -webkit-transform: rotate(-45deg);
    -ms-transform: rotate(-45deg);
    transform: rotate(-45deg);
    bottom: 9px;
  }
  .headerBurger.active span {
    -webkit-transform: scale(0);
    -ms-transform: scale(0);
    transform: scale(0);
  }
  .navigation-container.active {
    top: 0;
    -webkit-transition: all 0.8s ease 0s;
    -o-transition: all 0.8s ease 0s;
    transition: all 0.8s ease 0s;
  }
}

@keyframes minHeaderHeight {
  0% {
    height: 74px;
  }
  100% {
    height: 56px;
  }
}
@-o-keyframes minHeaderHeight {
  0% {
    height: 74px;
  }
  100% {
    height: 56px;
  }
}
@-moz-keyframes minHeaderHeight {
  0% {
    height: 74px;
  }
  100% {
    height: 56px;
  }
}
@-webkit-keyframes minHeaderHeight {
  0% {
    height: 74px;
  }
  100% {
    height: 56px;
  }
}
</style>
