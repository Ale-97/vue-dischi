<template>
  <div id="Header" class="header-container">
    <div class="container">
      <div class="row">
        <div class="col">
          <img src="../assets/spotify-logo.png" alt="" />
        </div>

        <div class="col-1">
          <select
            @click="$emit('search', filterString)"
            v-model="filterString"
            id="filter"
          >
            <option value="all">All</option>
            <option value="Rock">Rock</option>
            <option value="Pop">Pop</option>
            <option value="Jazz">Jazz</option>
            <option value="Metal">Metal</option>
          </select>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Header",
  data() {
    return {
      filterString: "all",
    };
  },
};
</script>

<style lang="scss" scoped>
.header-container {
  background-color: rgb(46, 58, 70);
  padding: 10px 0;
  .container {
  }
  img {
    width: 50px;
  }
}
</style>