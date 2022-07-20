<template>
  <div class="menu">
    <a v-for="(a,i) in menu" :key="i">{{ a }}</a>

  </div>
  <div v-for="(val,i) in products" :key="i">
    <h4>{{val}}</h4>
    <p>{{ i+100 }} 만원</p>
  </div>
</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      menu: ['Home', 'shop', 'about'],
      products: ['역삼동원룸', '천호동원룸', '마포구원룸']
    }
  },
  components: {}
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
