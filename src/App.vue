<template>

<ModalPopUp :oneRoomProducts ="oneRoomProducts" :clickProductIndex = clickProductIndex :modalIsOpen = modalIsOpen />

  <div class="menu">
    <a v-for="(a,i) in menu" :key="i">{{ a }}</a>
  </div>

  <Discount/>

  <div v-for="(oneRoomProduct,index) in oneRoomProducts" :key="index">
    <img :src="oneRoomProduct.image" class="room-img">
    <h4 @click="modalIsOpen = true; clickProductIndex = index">{{ oneRoomProduct.title }}</h4>
    <p>{{ oneRoomProduct.price }} 원</p>
  </div>
</template>

<script>
import ModalPopUp from './ModalPopUp.vue';
import oneRoomData from './assets/oneroom.js';
import Discount from './DiscountBanner.vue';

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
  components: {
    //컴포넌트 등록
    Discount : Discount,
    ModalPopUp : ModalPopUp,
  }
}
</script>

<style>
body {
  margin: 0;
}

div {
  box-sizing: border-box;
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

.white-bg img {
  width: 30%;
  height: 30%;
}
</style>
