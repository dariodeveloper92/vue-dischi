<template>
    <main>
        <section id="container-main">
            <div v-if="!loading" class="box-dischi row">
                <!-- Stampo la lista dei dischi ottenuta tramite Axios -->
                <div v-for="(disc, index) in discList" :key="index" class="col-6 col-md-5 col-lg-3 mb-5">
                    <Disc :cover="disc" />
                </div>
            </div>
            <!-- <Loader v-else /> -->
        </section>
    </main>
</template>

<script>
import axios from 'axios';
import Disc from './Disc.vue';
//import Loader from './Loader.vue';

export default {
  name: 'DiscList',
  components: {
      Disc,
      //Loader
  },
  data() {
    return {
      APIUrl: 'https://flynn.boolean.careers/exercises/api/array/music',
      discList: [],
      //loading: true
    }
  },
  created() {
    this.getDiscs(); 
  },
  methods: {
    getDiscs() {
      axios
          .get(this.APIUrl)
          .then( res => {
            console.log(res.data.response);
            this.discList = res.data.response;
            //setTimeout( () => {this.loading = false; }, 5000);
            //this.loading = false;
          })
          //.catch( err => {
            //console.log("Error ", err);
          //})
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

            .box-dischi {
                width: 100%;
                height: 100%;
            }
        }
    }
</style>