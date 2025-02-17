import get from "./assets/post.js";

<template>
  <div class="black-bg" v-if="modal_open == true">
    <div class="white-bg">
      <h3>집 상세내용</h3>
      <img :src=onerooms[click_number].image>
      <h4>{{ onerooms[click_number].title }}</h4> 
      <p>가격 : {{ onerooms[click_number].price }}</p>
      <p>{{ onerooms[click_number].content }}</p>
      <button @click="modal_open = false">닫기</button>
    </div>
  </div>

  <div class="menu">
    <a v-for="text in menus" :key="text">{{text}}</a>
    <a>Products</a>
    <a>About</a>
  </div>

  <Discount></Discount>

  <div v-for="a, i in onerooms" :key="i">
    <img class="image" :src=a.image>
    <h4 @click="modal_open = true; click_number = i">{{ a.title }}</h4>
    <p>{{ a.price }} 만원</p>
    <p>{{ a.content }}</p>
    <button @click="reports[i]++">허위매물신고</button> <span>신고수 : {{ reports[i] }}</span>
  </div>

</template>

<script>
import data from "./assets/post.js";
import DiscountBanner from "./DiscountBanner.vue";
import ModalWindow from "./ModalWindow.vue";

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
    Modal : ModalWindow
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
