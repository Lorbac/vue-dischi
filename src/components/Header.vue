<template>
  <header>
    <div class="logo">
      <img src="https://loghi-famosi.com/wp-content/uploads/2020/09/Logo-della-Spotify.png" alt="">
    </div>

    <form>
      <select @click="$emit('performSearch', inputText)" v-model="inputText" name="genre" id="genre">
        <option value="all">All</option>
        <option value="rock">Rock</option>
        <option value="pop">Pop</option>
        <option value="jazz">Jazz</option>
        <option value="metal">Metal</option>
      </select>
    </form>
  </header>
</template>

<script>
export default {
  name: 'Header',
  data() {
    return {
      inputText: "",
    }
  }
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
    display: flex;
    justify-content: space-between;

    img {
      height: 50px;
    }

    form {
      margin-right: 30px;
    }
  }
</style>
