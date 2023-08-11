<template>
  <div>
    <img :src="onerooms.image" class="room-img" @click="click" />
    <h4 @click="$emit('openModal', onerooms.id)">
      {{ onerooms.title }}
    </h4>
    <p>{{ onerooms.price }}</p>
  </div>
</template>
<script>
export default {
  name: "myCard",
  props: {
    onerooms: Object,
  },
  methods: {
    click() {
      console.log(this.onerooms);
    },
  },
};
</script>
<style></style>
