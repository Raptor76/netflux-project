<template>
  <div class="rowDiv">
    <h1>{{ genre }}</h1>

    <div class="divPage" :id="id">
      <div
        class="div"
        v-for="film in myfilm"
        v-bind:key="film"
        :style="'background-image: url(' + film.miniature + ')'"
      >
        <p>{{ film.title }}</p>
      </div>
    </div>
    <div class="btn">
      <button v-on:click="left()" id="left">&#x2B05;</button>
      <button v-on:click="right()" id="right">&#x27A1;</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "Film",
  props: ["myfilm", "genre", "id"],
  data() {
    return {
      color: "red",
    };
  },
  methods: {
    right() {
      document.getElementById(this.id).scrollBy({
        top: 0,
        left: 385,
        behavior: "smooth",
      });
    },
    left() {
      document.getElementById(this.id).scrollBy({
        top: 0,
        left: -385,
        behavior: "smooth",
      });
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.rowDiv {
  position: relative;
}

.btn {
  position: absolute;
  bottom: -40px;
  right: 0;
}

button {
  border: none;
  color: white;
  font-size: 50px;
  background: transparent;
  transition-duration: 0.4s;
}

button:hover {
  cursor: pointer;
  transform: scale(1.3);
}

.divPage {
  margin: auto;
  margin-left: 10px;
  overflow-x: hidden;
  overflow-y: hidden;
  display: grid;
  grid-template-columns: repeat(20, 385px);
  grid-template-rows: 220px;
  grid-column-gap: 0;
  grid-row-gap: 0px;
}

.div {
  position: relative;
  height: 200px;
  width: 350px;
  margin: auto;
  background-repeat: no-repeat;
  border-radius: 10px;
  background-size: contain;
  transition-duration: 0.4s;
}

.div:hover {
  transform: scale(1.1);
  cursor: pointer;
}

p {
  position: absolute;
  bottom: -17px;
  text-align: center;
  color: white;
  width: 91.5%;
  font-size: 20px;
  padding: 15px;
  background: linear-gradient(
    0deg,
    rgba(0, 0, 0, 1) 0%,
    rgba(0, 0, 0, 0.9248074229691877) 25%,
    rgba(0, 0, 0, 0.8127626050420168) 50%,
    rgba(0, 0, 0, 0.7567401960784313) 75%,
    rgba(0, 0, 0, 0) 100%
  );
  border-bottom-left-radius: 10px;
  border-bottom-right-radius: 10px;
}
h1 {
  color: white;
}
</style>
