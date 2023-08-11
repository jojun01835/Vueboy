<template>
  <div class="black-bg" v-if="Modal == true">
    <div class="white-bg">
      <h4>{{ onerooms[click].title }}</h4>
      <img :src="onerooms[click].image" :alt="onerooms[click].title" />
      <h4>{{ onerooms[click].price }}</h4>
      <p>{{ onerooms[click].content }}</p>
      <button @click="$emit('openclose')">❌</button>
    </div>
  </div>
</template>
<script>
export default {
  name: "myModal",
  props: {
    onerooms: Array,
    click: Number,
    Modal: Boolean,
  },
};
</script>
<style></style>
