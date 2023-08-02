<template>
  <div>
    <router-view />

  </div>
</template>
<script>
// import foot from "@/components/foot.vue";
// import navbar from "@/components/navbar.vue";
import index from './views/index.vue';

export default {
  // components: {
  //   navbar,
  //   foot,
  // },
  data() {
    return {};
  },
  mounted() {
  },
  components: { index }
};
</script>
<style>
:root {
  --main-color: #0b3643;
  --dark: #0b3643;
  --dark-light: #155e75;
  --light: eaeff5;
  --white: #ffffff; 
  --second-color: #f0f0f0;
}

* {
  font-family: "Cairo", sans-serif;
}

#app {
  font-family: "Cairo", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

</style>
