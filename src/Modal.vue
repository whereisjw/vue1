<template>
  <div class="black-bg" v-if="모달창열렸니">
    <div class="white-bg">
      <h4>{{ 원룸들[누른거].title }}</h4>
      <h3>{{ 원룸들[누른거].content }}</h3>
      <h3>{{ 원룸들[누른거].price }}</h3>

      <!--  <button v-on:click="모달창열렸니 = false">닫기</button> -->
    </div>
  </div>
  12
</template>
<script>
export default {
  name: "ModalItem",
  props: { 원룸들: Array, 누른거: Number, 모달창열렸니: Boolean },
};
</script>
<style></style>
