<template>
  <div class="black-bg" v-if="modalIsOpen == true">
    <div class="white-bg">
      <img :src="oneRoomProducts[clickProductIndex].image" style="width:100%">
      <h4>{{ oneRoomProducts[clickProductIndex].title }}</h4>
      <p>{{ oneRoomProducts[clickProductIndex].content }}</p>
      <p>{{ oneRoomProducts[clickProductIndex].price }} 원</p>
      <!-- props로 전달한 값은 read Only 이므로 변경 불가능     -->
      <!--<button @click="modalIsOpen=false">닫기</button>-->
    </div>
  </div>
</template>

<script>
export default {
  name: "ModalPopUp",
  props :{
    oneRoomProducts : Array ,
    clickProductIndex : Number ,
    modalIsOpen : Boolean ,
  }
}
</script>

<style scoped>
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
</style>