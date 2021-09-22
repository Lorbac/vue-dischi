<template>
    <div class="album m-2 text-center">
        <img class="img-fluid" :src="info.poster" :alt="info.title">
        <h2 class="fw-bold">{{ info.title }}</h2>
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
    @import '../styles/vars.scss';

    .album {
        background-color: $secondary-bg-color;
        height: 250px;

        img {
            padding: 15px;
            
        }
    
        h2 {
            color: white;
            text-transform: uppercase;
            font-size: 13px;
            padding: 5px;
        }
    
        p {
            color: gray;
            font-size: 10px;
            margin: 0;
        }
    }

    @media screen and (max-width: 992px) {
        .album {
            height: 400px;

            h2 {
                font-size: 20px;
            }

            p {
                font-size: 15px;
            }
        }
    }

    @media screen and (max-width: 768px) {
        .album {
            height: 500px;

            h2 {
                font-size: 30px;
            }

            p {
                font-size: 20px;
            }
        }
    }
</style>