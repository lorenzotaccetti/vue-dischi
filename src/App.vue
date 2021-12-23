<template>
  <div id="app">
    <Header />
    <MainList />
  </div>
</template>

<script>
import Header from './components/Header.vue';
import MainList from './components/MainList.vue'

export default {
  name: "App",
  components: {
    Header,
    MainList
  },
};
</script>

<style lang="scss">
@import '~@fontsource/montserrat/400.css';

*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body{
 font-family: "Montserrat"; 
}
</style>
