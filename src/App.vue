<template>

  <div class="menu">
    <a v-for="(value,index) in menu" :key="index">{{ value }}</a>
  </div>
<!--   <img alt="Vue logo" src="./assets/logo.png" />   -->

  <div v-for="(v,i) in products" :key="i">
    <h4>{{ v }}</h4>
    <h3>50만원</h3>
  </div>
 
</template>

<script>
export default {
  name: "App",
  data(){
    return{
      price1 : 60,
      price2 : 70,
      menu:['홈','상품','상세'],
    products:['역삼동원룸','천호동원룸','마포구원룸']
    }
  },
  components: {},
};
</script>

<style>
#app {
  
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
 
}
.menu{
  background-color: darkslateblue;
  padding: 15px;
  border-radius: 5px;

}
.menu a {
  color: white;
  padding: 10px;
}
</style>
