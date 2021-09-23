<template>
  <div id="app">
    <Header @performSearch="searchGenre" />

    <Dischi :filterDisc="inputText" />
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Dischi from './components/Dischi.vue'

export default {
  name: 'App',
  components: {
    Header,
    Dischi
  },
  data() {
    return {
      inputText: "",
    }
  },
  methods: {
    searchGenre(text) {
      this.inputText = text;
    }
  }
}
</script>

<style lang="scss">
  @import "./styles/general.scss"
</style>
