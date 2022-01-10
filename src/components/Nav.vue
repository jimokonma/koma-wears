<template>
  <div class="navbar">
    <nav>
      <img src="../assets/logo.png" alt="" class="logo" />
      <ul>
        <li>Home</li>
        <li><router-link to="/dashboard">Dashboard</router-link></li>
        <li v-on:click="$emit('displayCart')">
          Cart
          <span class="cartNotify">
            {{ cart.length }}
          </span>
        </li>
      </ul>
    </nav>
  </div>
</template>
<script>
export default {
  name: "Nav",
  components: {},
  props: ["cart"],
};
</script>

<style scoped>
.navbar {
  width: 100%;
  background: #ffffff;
  height: 60px;
  position: fixed;
}
nav {
  width: 60%;
  height: 60px;
  color: #9dc79f;
  margin: 0px auto;
  display: flex;
  justify-content: space-between;
  align-items: center;
  z-index: 1;
}
ul {
  width: 300px;
  list-style: none;
  display: flex;
  justify-content: space-evenly;
}
.cartNotify {
  width: 20px;
  height: 20px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 0.8em;
  background: #fa6767;
  color: white;
  border-radius: 50%;
  border: 2px solid #ffffff;
  position: absolute;
  right: -15px;
  top: -8px;
}
li:last-child {
  position: relative;
  cursor: pointer;
}
</style>
