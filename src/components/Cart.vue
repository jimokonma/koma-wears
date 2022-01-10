<template>
  <div class="cart" :class="{ display: showCart }">
    <span class="cart-header">
      <h3>Shopping Cart</h3>
      <button class="close-cart" v-on:click="$emit('close-cart')">X</button>
    </span>

    <span class="cart-item" :key="item.id" v-for="item in cart">
      <img v-bind:src="item.img" v-bind:alt="item.name" />
      <h5>
        <!-- <button class="mini-btn" @click="$emit('reduceItemsInCart', item.id)">
          -</button
        > -->
        {{ item.numberOfItems }}
        <!-- <button class="mini-btn" @click="$emit('increaseItemsInCart', item.id)">
          +
        </button> -->
      </h5>
      <p>{{ item.name }}</p>
      <h5>N{{ (item.numberOfItems * item.price).toLocaleString() }}</h5>
      <span @click="$emit('remove-from-cart', item.id)" class="remove">x</span>
    </span>

    <span v-if="cart.length > 0">
      <h3>Total: {{ cartTotal.toLocaleString() }}</h3>
      <button class="btn" @click="$emit('check-out', cartTotal)">
        Check out
      </button>
    </span>
    <span v-else>
      <h4>Cart is empty</h4>
    </span>
  </div>
</template>
<script>
export default {
  name: "Cart",
  props: ["showCart", "cart", "cartTotal"],
};
</script>
<style scoped>
.cart {
  width: 100vw;
  max-width: 400px;
  height: 100vh;
  padding: 50px 10px;
  background: #ffffffee;
  display: none;
  position: absolute;
  position: fixed;
  top: -20px;
  right: -40vw;
  z-index: 10;
  overflow-y: scroll;
  box-shadow: 5px 5px 5px 5px;
  transition: 4s ease-out;
}
.display {
  display: block;
  right: 0vw;
  transition: right 15s;
}
.cart-item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin: 15px 0px;
  padding: 5px 0px;
  font-size: 15px;
  border-bottom: 1px solid rgb(231, 231, 231);
}
.cart-item > img {
  width: 60px;
  display: flex;
  z-index: 1;
}
.remove {
  color: #e68c8c;
  cursor: pointer;
}
button {
  border: none;
  color: #9dc79f;
  background: none;
  cursor: pointer;
}
.cart-header {
  display: flex;
  justify-content: space-between;
}
.btn {
  width: 100px;
  padding: 10px;
  margin: 0px auto;
  color: #ffffff;
  background: #e68c8c;
}
h4 {
  color: #c1ddc2;
  text-align: center;
  margin-top: 40vh;
}
</style>
