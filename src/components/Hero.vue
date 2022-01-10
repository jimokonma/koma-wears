<template>
  <div class="hero">
    <Nav v-bind:cart="cart" @displayCart="$emit('displayCart')" />
    <header>
      <div class="holder">
        <div class="textHolder">
          <h1>Fashion</h1>
          <h2>For <em style="color: #9dc79f">You</em></h2>
        </div>
      </div>
    </header>
  </div>
</template>
<script>
import Nav from "./Nav";
export default {
  name: "Hero",
  components: {
    Nav,
  },
  props: ["cart"],
  data() {
    return {
      search: "",
    };
  },
  methods: {
    filter() {
      console.log(this.search + "searching.....");
    },
  },
};
</script>

<style scoped>
header {
  height: 500px;
  background: url("../assets/Path 8.svg");
  background-size: cover;
  /* background: #9dc79f; */
}
.holder {
  width: 100%;
  max-width: 780px;
  margin: auto;
  padding: 100px 0px;
}

.textHolder > h1 {
  font-size: 5em;
  font-weight: normal;
}
.textHolder > h2 {
  font-size: 3em;
  font-weight: normal;
  margin-bottom: 20px;
}

.imageHolder {
  height: 300px;
  flex: 50%;
  position: relative;
}

button {
  padding: 10px;
  border: none;
  border-radius: 5px;
  background: white;
}
</style>
