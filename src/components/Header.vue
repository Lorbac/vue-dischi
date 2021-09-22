<template>
  <header>
    <div class="logo">
      <img src="https://loghi-famosi.com/wp-content/uploads/2020/09/Logo-della-Spotify.png" alt="">
    </div>
  </header>
</template>

<script>
export default {
  name: 'Header',
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  @import '../styles/vars.scss';

  header{
    background-color: $secondary-bg-color;
    width: 100%;
    height: 90px;
    line-height: 90px;

    img {
      height: 50px;
    }
  }
</style>
