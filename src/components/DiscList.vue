<template>
    <main>
        <section id="container-main">
            <div v-if="!loading" class="box-dischi row">
              <div  class="col-12">
                <Search @performSearch="searchGenre" />
              </div>
                <!-- Stampo la lista dei dischi ottenuta tramite Axios -->
                <!-- SOSTITUIRE discList in filteredList -->
                <div v-for="(disc, index) in filteredGenreList" :key="index" class="col-4 col-md-4 col-lg-2 mb-2">
                    <Disc :cover="disc" /> <!-- cicla gli elementi contenuti nella componente Disc che mi sono creato -->
                </div>
            </div>
            <Loader v-else />
        </section>
    </main>
</template>

<script>
import axios from 'axios';
import Disc from './Disc.vue';
import Loader from './Loader.vue';
import Search from './Search.vue';

export default {
  name: 'DiscList',
  components: {
      Disc,
      Loader,
      Search
  },
  data() {
    return {
      APIUrl: 'https://flynn.boolean.careers/exercises/api/array/music',
      discList: [],
      loading: true,
      searchText: ''
    }
  },
  created() {
    this.getDiscs(); 
  },
  computed: {
    filteredGenreList() {
      if(this.discList.length > 0){
        if(this.searchText == ''){
          return this.discList;
        }
        let filteredList = this.discList.filter(item => {
          return item.genre
                          .toLowerCase()
                          .includes(this.searchText.toLowerCase());
        })
        return filteredList;
      }
      return this.discList;
    }
  },
  methods: {
    getDiscs() {
      axios
          .get(this.APIUrl) //per lanciare l'array di oggetti contenuti nell'API
          .then( res => {
            console.log(res.data.response);
            this.discList = res.data.response;
            //setTimeout( () => {this.loading = false; }, 5000);
            this.loading = false;
          })
          .catch( err => {//nel caso di errore lo stampa in console
            console.log("Error ", err);
          })
    },
    searchGenre(text) {
      console.log(text);
      this.searchText = text;
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
    main {
        width: 100%;
        height: 90vh;
        background-color: #1A253A;

        #container-main {
            width: 100%;
            height: 100%;
            padding: 30px;
            display: flex;
            justify-content: center;
            position: relative;

            .box-dischi {
                width: 70%;
                height: 100%;
                //background-color: white;
                position: relative;
                display: flex;
                justify-content: center;
            }
        }
    }
</style>