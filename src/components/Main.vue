<template>
    <div id="Main">
        <div class="container ">
            <div class="row">
        <Album v-for="(album, index) in albums " 
        :key='index'
        :album='album'
        class="col-2 "/>
            </div>
        </div>
    </div>
</template>

<script>
import Album from "./Album.vue";

export default {
 name:"Main",
 props:{
     albums:Array,
 },
  components:{
     Album,
  }
}
</script>

<style lang="scss" scoped>

</style>