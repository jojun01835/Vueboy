<template>
  <Modal :onerooms="onerooms" :click="click" :Modal="Modal" @openclose="ModalClose" />
  <div class="menu">
    <a v-for="floop in menus" :key="floop">{{ floop }}</a>
  </div>
  <Discnt />
  <Card
    v-bind:onerooms="onerooms[i]"
    @openModal="
      handleCardClick();
      click = $event;
    "
    v-for="(a, i) in onerooms"
    :key="i"
  />
</template>

<script>
import data from "./oneroom";
import Discnt from "./Discnt.vue";
import Modal from "./Modal.vue";
import Card from "./Card.vue";

export default {
  name: "App",
  data() {
    return {
      click: 0,
      onerooms: data,
      Modal: false,
      report: [0, 0, 0],
      menus: ["Home", "products", " About"],
      products: ["역삼동원룸", "천호동원룸", "마포구원룸"],
    };
  },
  methods: {
    increase(idx) {
      this.report[idx] += 1;
    },
    handleCardClick() {
      this.Modal = true; // 수정: Modal 값을 true로 설정
    },
    ModalClose() {
      this.Modal = false;
    },
  },
  components: {
    Discnt,
    Modal,
    Card,
  },
};
</script>

<style>
body {
  margin: 0;
}
div {
  box-sizing: border-box;
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
.room-img {
  width: 100%;
  margin-top: 40px;
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

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
