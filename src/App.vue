<template>
  <ModalItem
    v-on:close="모달창열렸니 = false"
    :원룸들="원룸들"
    :누른거="누른거"
    :모달창열렸니="모달창열렸니" />

  <div class="menu">
    <a v-for="(value, index) in menu" :key="index">{{ value }}</a>
  </div>

  <div class="discount" v-if="showDiscount">
    <h4>지금 결제하면 20% 할인</h4>
  </div>
  <button v-on:click="priceSort">가격순정렬</button>
  <button v-on:click="reversePriceSort">가격역순정렬</button>
  <button v-on:click="ganadaFn">가나다순정렬</button>
  <button v-on:click="sortBack">되돌리기</button>
  <RoomItem
    v-on:openModal="모달창열렸니 = true"
    v-on:changePress="누른거 = i"
    :누른거="누른거"
    :원룸들="원룸들"
    :모달창열렸니="모달창열렸니"
    :신고수="신고수" />
</template>
<script>
import ModalItem from "./Modal.vue";
import roomData from "./oneroom.js";
import RoomItem from "./RoomItem.vue";

export default {
  name: "App",
  data() {
    return {
      showDiscount: false,
      원룸들오리지날: [...roomData],
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
    reversePriceSort() {
      this.원룸들.sort(function (a, b) {
        return b.price - a.price;
      });
    },
    sortBack() {
      this.원룸들 = [...this.원룸들오리지날];
    },
    priceSort() {
      this.원룸들.sort(function (a, b) {
        return a.price - b.price;
      });
    },
    increase(a) {
      this.신고수[a] = this.신고수[a] + 1;
    },
  },
  mounted() {
    setTimeout(() => {
      this.showDiscount = true;
    }, 2000);
  },
  components: { ModalItem, RoomItem },
};
</script>

<style>
.fade-enter-from {
  opacity: 0;
}
.fade-enter-active {
  transition: all 1s;
}
.fade-enter-to {
  opacity: 1;
}

.start {
  opacity: 0;
  transition: all 1s linear;
}
.end {
  opacity: 1;
}
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
