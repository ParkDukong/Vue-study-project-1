<template>

  <div class="menu">
    <a v-for="text in menus" :key="text">{{text}}</a>
    <a>Products</a>
    <a>About</a>
  </div>
  <div v-for="a, i in products" :key="i">
    <h4>{{ a }}</h4>
    <p>{{ prices[i] }} 만원</p>
    <button @click="reports[i]++">허위매물신고</button> <span>신고수 : {{ reports[i] }}</span>
  </div>

</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      reports : [0, 0, 0],
      menus : ["Home", "Shop", "About"],
      prices : ["70", "110", "30"],
      products : ["역삼동원룸", "천호동원룸", "마포구원룸룸"]
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 10px;
}
</style>
