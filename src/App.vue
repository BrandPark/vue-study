<template>
  <div class="menu">
    <a v-for="(title, i) in navigates" :key="i">{{title}}</a>

  </div>


  <div>
    <h4 v-for="(product, i) in products" :key="i">{{product}}</h4>
  </div>

</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
      navigates : ['Home', 'Shop', 'About'],
      price : [50, 60, 70],
    }
  },

  components: {
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
