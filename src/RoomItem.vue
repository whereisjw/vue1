<template>
  <div v-for="(v, i) in 원룸들" :key="i">
    <img
      v-on:click="$emit('openModal')"
      class="room_img"
      :src="v.image"
      alt="" />
    <h4 v-on:click="$emit('changePress')">
      {{ v.title }}
    </h4>
    <p>{{ v.price }}원</p>
    <button v-on:click="increase(0)">허위매물신고버튼</button>
    <span>신고수 : {{ 신고수[0] }}</span>
  </div>
</template>
<script>
export default {
  name: "RoomItem",
  props: {
    누른거: Number,
    원룸들: Array,
    모달창열렸니: Boolean,
    신고수: Array,
  },
};
</script>
<style></style>
