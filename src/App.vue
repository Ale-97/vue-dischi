<template>
  <div id="app" >
    <Header />
    <Main :albums="albums" />
  </div>
</template>

<script>

import axios from "axios";
import Header from "./components/Header.vue";
import Main from "./components/Main.vue";

export default {
  name: "App",
  components: {
    Main,
    Header,
  },

  data() {
    return {
      albums: "",
    };
  },

  created() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((result) => {
        this.albums = result.data.response;
      });
  },
  
};

</script>

<style lang="scss">
</style>
