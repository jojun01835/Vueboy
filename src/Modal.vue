<template>
  <div class="black-bg" v-if="Modal == true">
    <div class="white-bg">
      <h4>{{ onerooms[click].title }}</h4>
      <img :src="onerooms[click].image" :alt="onerooms[click].title" />
      <h4>{{ onerooms[click].price }}</h4>
      <p>{{ onerooms[click].content }}</p>
      <button @click="Modal = false">❌</button>
    </div>
  </div>
</template>
<script>
export default {
  name: "myModal",
};
</script>
<style></style>
