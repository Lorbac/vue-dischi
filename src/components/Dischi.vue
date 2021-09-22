<template>
  <main>
      <div class="container">
          <div class="row">
                <div class="col-12 col-md-5 col-lg-2" v-for="(album,index) in albumList" :key="index">
                    <Disco :info="album"/>
                </div>
          </div>
      </div>
  </main>
</template>

<script>
import axios from "axios";
import Disco from "../components/Disco.vue"

export default {
    name: 'Main',
    components: {
        Disco,
    },
    data() {
        return {
            APIUrl: "https://flynn.boolean.careers/exercises/api/array/music",
            albumList: []
        }
    },
    created() {
        this.getAlbums();
    },
    methods: {
        getAlbums() {
            axios
                .get(this.APIUrl)
                .then(res => {
                    // console.log(res.data.response);
                    this.albumList = res.data.response;
                    res.data.success = false;
                })
                .catch( err => {
                    console.log("Error ", err);
                })
        }
    },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
    @import '../styles/vars.scss';

    main {
        background-color: $primary-bg-color;
        height: calc(100vh - 90px);
        
        .container {
            .row {

                width: 80%;
                margin: 0 auto; 

                .col-12 {
                    border: 20px solid #1E2D3C;
                    background-color: $secondary-bg-color;
                }
            }
        }
    }

</style>