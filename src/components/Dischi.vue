<template>
  <main>
      <div class="container">
          <div v-if="success" class="row py-5">
                <div class="col-12 col-md-5 col-lg-2" v-for="(album,index) in filteredAlbumList" :key="index">
                    <Disco :info="album"/>
                </div>
          </div>

          <Loader v-else />
      </div>

  </main>
</template>

<script>
import axios from "axios";
import Disco from "../components/Disco.vue";
import Loader from './Loader.vue';

export default {
    name: 'Dischi',
    props: ["filterDisc"],
    components: {
        Disco,
        Loader
    },
    data() {
        return {
            APIUrl: "https://flynn.boolean.careers/exercises/api/array/music",
            albumList: [],
            success: false,
            listGenre:[],
        }
    },
    created() {
        this.getAlbums();
        
    },
    computed: {
        filteredAlbumList() {
        if (this.filterDisc === "all") {
            return this.albumList;
        }

        let filteredList = this.albumList.filter( item => {
            return item.genre.toLowerCase().includes(this.filterDisc);
        })

        return filteredList;
        },
    },
    methods: {
        getAlbums() {
            axios
                .get(this.APIUrl)
                .then(res => {
                    // console.log(res.data.response);
                    this.albumList = res.data.response;
                    this.success = res.data.success;

                    this.albumList.forEach((disc) => {
                        if (this.listGenre.includes(disc.genre) == false) 
                        {
                            this.listGenre.push(disc.genre);
                        }
                    });
                })
                .catch( err => {
                    console.log("Error ", err);
                })
        },
    },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
    @import '../styles/vars.scss';

    main {
        background-color: $primary-bg-color;
        height: calc(100vh - 90px);
        overflow-y: auto;
        
        .container {
            .row {

                width: 80%;
                margin: 0 auto; 
            }
        }
    }

</style>