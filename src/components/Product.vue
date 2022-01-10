<template>
  <div>
    <div class="product">
      <img v-bind:src="item.img" v-bind:alt="item.price" />
      <p>
        {{ item.name }}
      </p>
      <h3 v-if="cart.every((product) => product.id != item.id)">
        <button @click="decrement" :class="color">-</button>
        {{ numberOfItems }}
        <button @click="increment" class="mini-btn">+</button>
      </h3>
      <div>
        <h4>N{{ item.price.toLocaleString() }}</h4>
        <button
          class="btn"
          v-on:click="addToCart(numberOfItems)"
          v-if="cart.every((product) => product.id != item.id)"
        >
          Add to cart
        </button>
        <p v-else class="small-text">product in Cart</p>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "Product",
  props: ["item", "cart"],
  data() {
    return {
      numberOfItems: 1,
      color: "mini-btn disabled", //cart items + and - button style
    };
  },
  methods: {
    increment() {
      this.numberOfItems++;
      // this.$props.cart.map((m) =>
      //   m.id === this.$props.item.id
      //     ? { ...m, numberOfItems: this.numberOfItems }
      //     : m
      // );
      this.color = this.numberOfItems === 1 ? "mini-btn disabled" : "mini-btn";
    },
    decrement() {
      if (this.numberOfItems !== 1) this.numberOfItems--;
      this.color = this.numberOfItems === 1 ? "mini-btn disabled" : "mini-btn";
    },
    addToCart(numberOfItems) {
      this.$emit("add-cart", { ...this.item, numberOfItems });
    },
  },
};
</script>
<style scoped>
.product {
  width: 200px;
  height: 300px;
  margin: 20px;
  text-align: center;
}
.product > div {
  display: flex;
  justify-content: space-evenly;
  align-items: center;
}

img {
  width: 100%;
  height: 65%;
}
</style>