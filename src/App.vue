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
      filtredAlbums: [],
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
  methods: {
    searchGenre(filterString) {
      return (this.filtredAlbums = this.albums.filter((genere) => {
        if (filterString === "all") {
          //se si selezziona 'all' restituirà tutti i valori
          return true;
        }
        if (filterString === genere.genre) {
          //se la nostra selezione coincide con il tipo dell'oggeto in esame ci restituirà quell'oggetto
          return true;
        }
        return false; //se nessuna condizione viene esaudita non restituirà nulla
      }));
    },
  },
};
</script>

<style lang="scss">
#app {
  background: rgb(30, 45, 59);
  min-height: 100vh;
}
</style>
