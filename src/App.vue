<template>
  <MainCard/>
</template>

<script>
import MainCard from './components/MainCard.vue';

export default {
  name: 'App',
  components: {
    MainCard
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2a3d50;
  margin-top: 60px;
}
</style>
