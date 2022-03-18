<template>
  <div class="menu">
    <a v-for="(title, i) in navigates" :key="i">{{title}}</a>
  </div>

  <div class="black-bg" v-if="모달창열렸니">
      <div class="white-bg">
        <h4>상세페이지임</h4>
        <p>상세페이지 내용임</p>
        <button @click="모달창열렸니 = false">닫기</button>
      </div>
  </div>

  <div v-for="(원룸, i) in 원룸들" :key="i">
    <img :src="원룸.image">
    <h4 @click="모달창열렸니 = true">{{원룸.title}}</h4>
    <p>{{원룸.price}}원</p>
    <button @mouseover="increase(i)">허위매물신고</button> <span>신고수 : {{신고수[i]}}</span>
  </div>

</template>

<script>

import oneroomData from './assets/oneroom.js';

export default {
  name: 'App',
  data() {
    return {
      원룸들 : oneroomData,
      모달창열렸니 : false,
      신고수 : [0, 0, 0],
      products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
      navigates : ['Home', 'Shop', 'About'],
      price : [50, 60, 70],
    }
  },
  methods: {
    increase(idx) {
      this.신고수[idx]++;
    }
  },
  components: {
  }
}
</script>

<style>
body{
  margin: 0;
}
div {
  box-sizing: border-box;
}
.black-bg {
  width: 100%; height: 100%;
  background: rgba(0,0,0,0.5);
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
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 10px;
}
</style>
