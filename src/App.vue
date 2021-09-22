<template>
  <div id="app">
    <Header />

    <Dischi />
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
  }
}
</script>

<style lang="scss">
  @import "./styles/general.scss"
</style>
