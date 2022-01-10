<template>
  <div class="holder">
    <div v-for="item in products" :key="item.id">
      <Product :item="item" @add-cart="addCartItem" :cart="cart" />
    </div>
  </div>
</template>

<script>
import Product from "./Product";
export default {
  name: "Products",
  components: {
    Product,
  },
  props: ["products", "cart"],
  methods: {
    addCartItem(newProduct) {
      this.$emit("add-cart", newProduct);
    },
  },
};
</script>

<style scoped>
.holder {
  width: 100%;
  max-width: 1000px;
  margin: 50px auto;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}
</style>