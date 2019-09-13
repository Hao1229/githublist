<template>
  <div id="app">
    <GithubList/>
  </div>
</template>

<script>
import GithubList from './components/GithubList.vue'
export default {
  name: 'app',
  components: {
    GithubList
  }
}
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap";
@import url('https://fonts.googleapis.com/css?family=Noto+Sans+TC&display=swap');
#app {
  font-family: 'Noto Sans TC', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
