<template>

  <div class="black-bg" v-if="modalIsOpen == true">
    <div class="white-bg">
      <h4>상세페이지임</h4>
      <p>상세페이지 내용임</p>
      <button @click="modalIsOpen=false">닫기</button>
    </div>
  </div>

  <div class="menu">
    <a v-for="(a,i) in menu" :key="i">{{ a }}</a>
  </div>
  <div>
    <img :src="oneRoomProducts[0].image" class="room-img">
    <h4 @click="modalIsOpen = true">{{ oneRoomProducts[0].title }}</h4>
    <p>{{oneRoomProducts[0].price}} 만원</p>
  </div>
  <div>
    <img src="./assets/room1.jpg" class="room-img">
    <h4>{{ products[1] }}</h4>
    <p>50 만원</p>
  </div>
  <div>
    <img src="./assets/room2.jpg" class="room-img">
    <h4>{{ products[2] }}</h4>
    <p>60 만원</p>an>
  </div>
</template>

<script>
import oneRoomData from './assets/oneroom.js';

export default {
  name: 'App',
  data() {
    return {
      oneRoomProducts : oneRoomData,
      modalIsOpen: false,
      신고수: [0, 0, 0],
      menu: ['Home', 'shop', 'about'],
      products: ['역삼동원룸', '천호동원룸', '마포구원룸']
    }
  }, methods: {
    increase(i) {
      this.신고수[i] += 1;
    },
  },
  components: {}
}
</script>

<style>
body {
  margin: 0;
}

div {
  box-sizing: border-box;
}

.black-bg {
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  padding: 20px;
}

.white-bg {
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}

.room-img {
  width: 100%;
  margin-top: 40px;
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
