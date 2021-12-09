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

export default ({
 name:"Main",
 props:{
     albums:Object,
 },
  components:{
     Album,
  }
})
</script>

<style lang="scss" scoped>
#Main{
    background: rgb(30, 45, 59);
}

</style>