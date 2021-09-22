<template>
    <div class="album m-2 text-center">
        <img class="img-fluid" :src="info.poster" :alt="info.title">
        <h2 class="fw-bold mt-2">{{ info.title }}</h2>
        <p>{{ info.author }}</p>
        <p>{{ info.year }}</p>
    </div>
</template>

<script>
export default {
  name: 'Disco',
  props: ["info"]
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

    .album {

        img {
            width: 100%;
        }
    
        h2 {
            color: white;
            text-transform: uppercase;
            font-size: 13px;
        }
    
        p {
            color: gray;
            font-size: 10px;
            margin: 0;
        }
    }
</style>