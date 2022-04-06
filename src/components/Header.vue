<template>
  <div class="div">
    <header>
      <img src="../assets/Netflux.png" />
      <div class="btn">
        <a href="">Inscription</a>
        <a href="">Connection</a>
        <a href="">Aide</a>
      </div>
    </header>
  </div>
</template>

<script>
export default {};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.div {
  margin-bottom: 100px;
}
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  top: 0;
  left: 0;
  width: 100%;
  position: fixed;
  background: black;
  z-index: 1;
}
.btn {
  display: flex;
  justify-content: space-evenly;
  font-size: 20px;
  align-items: baseline;
  width: 400px;
}
a {
  color: white;
  text-decoration: none;
}
</style>
