/* eslint-disable */
import get from "./assets/post.js";

<template>
  <Modal :onerooms = "onerooms" :click_number = "click_number" :modal_open = "modal_open"></Modal>

  <div class="menu">
    <a v-for="text in menus" :key="text">{{text}}</a>
    <a>Products</a>
    <a>About</a>
  </div>

  <Discount></Discount>

  <Home :oneroom="onerooms[i]" v-for="(a, i) in onerooms" :key="i"></Home>
  <p>{{ onerooms }}</p>

</template>

<script>
import data from "./assets/post.js";
import DiscountBanner from "./DiscountBanner.vue";
import ModalWindow from "./ModalWindow.vue";
import HomeView from "./HomeView.vue";

export default {
  name: 'App',
  data() {
    return {
      onerooms : data,
      reports : [0, 0, 0, 0, 0, 0, 0, 0, 0, 0],
      menus : ["Home", "Shop", "About"],
      prices : ["70", "110", "30"],
      products : ["역삼동원룸", "천호동원룸", "마포구원룸룸"],
      modal_open : false,
      click_number : 0
    }
  },
  methods : {
    function_name() {

    }
  },
  components: {
    Discount : DiscountBanner,
    Modal : ModalWindow,
    Home : HomeView
  }
}

</script>

<style>
body {
  margin: 0
}
div {
  box-sizing: border-box;
}
.black-bg {
  width: 100%; height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed; padding: 20px;
}
.white-bg {
  width: 100%; background: white;
  border-radius: 8px;
  padding: 20px;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu {
  background: darkslateblue;
  padding: 15px;;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 10px;
}
</style>
