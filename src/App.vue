<template>

  <div class="black-bg" v-if="modalIsOpen == true">
    <div class="white-bg">
      <h4>{{ oneRoomProducts[clickProductIndex].title }}</h4>
      <img :src="oneRoomProducts[clickProductIndex].image">
      <p>{{ oneRoomProducts[clickProductIndex].content }}</p>
      <p>{{ oneRoomProducts[clickProductIndex].price}} 원</p>
      <button @click="modalIsOpen=false">닫기</button>
    </div>
  </div>

  <div class="menu">
    <a v-for="(a,i) in menu" :key="i">{{ a }}</a>
  </div>
  <div v-for="(oneRoomProduct,index) in oneRoomProducts" :key="index">
    <img :src="oneRoomProduct.image" class="room-img">
    <h4 @click="modalIsOpen = true; clickProductIndex = index">{{ oneRoomProduct.title }}</h4>
    <p>{{ oneRoomProduct.price }} 원</p>
  </div>
</template>

<script>
import oneRoomData from './assets/oneroom.js';

export default {
  name: 'App',
  data() {
    return {
      clickProductIndex: 0,
      oneRoomProducts: oneRoomData,
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
.white-bg img{
  width: 30%;
  height: 30%;
}
</style>
