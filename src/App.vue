<template>
<!--  <div-->
<!--      class="w-full bg-center bg-cover"-->
<!--      :style="{ backgroundImage: 'url(./assets/background.png)' }"-->
<!--      style='height: calc(100vh - 3rem);'-->
<!--  >-->
<!--  </div>-->

  test
    <img
        src="./assets/background.png"
        class="h-screen bg-center bg-cover"
    >
</template>

<script>


export default {
  name: 'App',
  components: {
  },
  data() {
    return {
      bgImage: "./assets/background.png"
    };
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
