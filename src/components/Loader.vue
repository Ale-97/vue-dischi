<template>
  <div id="Loader">Loading...</div>
</template>

<script>
export default {
  name: "Loader",
};
</script>

<style lang="scss" scoped>
div {
  position: fixed;
  width: 100vw; 
  height: 100vh;
  background: white;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 50px;
  font-weight: bold;
}
</style>
