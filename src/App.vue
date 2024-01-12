<template>
  <ModalItem :원룸들="원룸들" :누른거="누른거" :모달창열렸니="모달창열렸니" />

  <div class="menu">
    <a v-for="(value, index) in menu" :key="index">{{ value }}</a>
  </div>

  <div class="discount">
    <h4>지금 결제하면 20% 할인</h4>
  </div>
  <RoomItem />
  <div v-for="(v, i) in 원룸들" :key="i">
    <img class="room_img" :src="v.image" alt="" />
    <h4
      v-on:click="
        모달창열렸니 = true;
        누른거 = i;
      ">
      {{ v.title }}
    </h4>
    <p>{{ v.price }}원</p>
    <button v-on:click="increase(0)">허위매물신고버튼</button>
    <span>신고수 : {{ 신고수[0] }}</span>
  </div>
</template>
<script>
import ModalItem from "./Modal.vue";
import roomData from "./oneroom.js";
import RoomItem from "./RoomItem.vue";
export default {
  name: "App",
  data() {
    return {
      누른거: 0,
      원룸들: roomData,
      모달창열렸니: false,
      신고수: [0, 0, 0],
      price1: 60,
      price2: 70,

      menu: ["홈", "상품", "상세"],
      products: ["역삼동원룸", "천호동원룸", "마포구원룸"],
    };
  },
  methods: {
    increase(a) {
      this.신고수[a] = this.신고수[a] + 1;
    },
  },
  components: { ModalItem, RoomItem },
};
</script>

<style>
body {
  margin: 0;
}
div {
  box-sizing: border-box;
}
.discount {
  background: gray;
  padding: 20px;
  margin: 10px;
  box-sizing: border-box;
  border: 1px solid black;
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
.room_img {
  margin-top: 40px;
  width: 100%;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.menu {
  background-color: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}
.menu a {
  color: white;
  padding: 10px;
}
</style>
