<template>
  <div id="app">
    <public-header></public-header>

    <div class="contents">
      <router-view />
    </div>

    <public-footer></public-footer>
  </div>
</template>

<script>
import PublicFooter from './components/PublicFooter.vue'
import PublicHeader from './components/PublicHeader.vue'
export default {
  components: {
    PublicHeader,
    PublicFooter
  }
}
</script>

<style>
body {
  margin: 0;
}

/* #app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
} */

</style>
