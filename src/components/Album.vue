<template>
    <div id="Album" >
        <div class="container-img">
            <img :src="album.poster" alt="">
        </div>
        <h4>{{album.title}}</h4>
        <div>{{album.author}}</div>
        <div>{{album.year}}</div>
    </div>
</template>

<script>

export default {
 name:"Album",
 props:{
     album:Object,
 }

}
</script>

<style lang="scss" scoped>
.col-2{
    margin: 40px 15px;
    padding: 20px;
    text-align: center;
    background: rgb(46, 58, 70);
    color: rgb(128, 109, 93);
    h4{
        margin: 0 0  20px 0;
        color: white
    };
    .container-img{
        height: 190px;
        img{
            width: 100%;
        }
    }
}
</style>