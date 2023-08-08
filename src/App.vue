<template>
  <div class="menu">
    <a v-for="floop in menus" :key="floop">{{ floop }}</a>
  </div>

  <div>
    <h4>{{ products[0] }}</h4>
    <p>50만원</p>
    <button @click="increase(0)">허위매물신고</button> <span>신고수 : {{ report[0] }}</span>
  </div>
  <div>
    <h4>{{ products[1] }}</h4>
    <p>70만원</p>
    <button @click="increase(1)">허위매물신고</button> <span>신고수 : {{ report[1] }}</span>
  </div>
  <div>
    <h4>{{ products[2] }}</h4>
    <p>40만원</p>
    <button @click="increase(2)">허위매물신고</button> <span>신고수 : {{ report[2] }}</span>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      report: [0, 0, 0],
      menus: ["Home", "products", " About"],
      products: ["역삼동원룸", "천호동원룸", "마포구원룸"],
    };
  },
  methods: {
    increase(idx) {
      this.report[idx] += 1;
    },
  },
  components: {},
};
</script>

<style>
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
