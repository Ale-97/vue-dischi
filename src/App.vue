<template>
  <div id="app">
    <Loader v-if="albums.length == 0" />
    <Header @search="searchGenre" />
    <Main :albums="filtredAlbums" />
  </div>
</template>

<script>
import Loader from "./components/Loader.vue";
import axios from "axios";
import Header from "./components/Header.vue";
import Main from "./components/Main.vue";

export default {
  name: "App",
  components: {
    Loader,
    Main,
    Header,
  },

  data() {
    return {
      albums: [],
      inmputSearch: "",
    };
  },

  created() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((result) => {
        this.albums = result.data.response;
        this.searchGenre("all");
      });
  },
  computed:{
    filtredAlbums(){
      return this.albums.filter((genere) => {
        let filtro = this.inmputSearch
        if (filtro === "all") {
          //se si selezziona 'all' restituirà tutti i valori
          return true;
        }
        if (filtro === genere.genre) {
          //se la nostra selezione coincide con l'oggeto in esame ci restituirà quell'oggetto
          return true;
        }
        return false; //se nessuna condizione viene esaudita non restituirà nulla
      });
    },
      
    },
  methods: {
    searchGenre(filterString) {
      return this.inmputSearch = filterString
      }
  },
};
</script>

<style lang="scss">
#app {
  background: rgb(30, 45, 59);
  min-height: 100vh;
}
</style>
