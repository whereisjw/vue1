<template>
  <Transition name="fade">
    <div class="black-bg" v-if="모달창열렸니">
      <div class="white-bg">
        <h4>{{ 원룸들[누른거].title }}</h4>
        <h3>{{ 원룸들[누른거].content }}</h3>
        <input type="number" v-model="month" />
        개월
        <h3>{{ month }}개월 총 {{ 원룸들[누른거].price * month }}원</h3>

        <button v-on:click="$emit('close')">닫기</button>
      </div>
    </div>
  </Transition>
  12
</template>
<script>
export default {
  name: "ModalItem",
  data() {
    return {
      month: 1,
    };
  },
  watch: {
    month(a, b) {
      if (a > 10) this.month = 1;
    },
  },
  props: { 원룸들: Array, 누른거: Number, 모달창열렸니: Boolean },
};
</script>
<style></style>
