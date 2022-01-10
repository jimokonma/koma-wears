<template>
  <!-- Notification bar -->
  <Notification
    :notification="notification"
    :notificationBackgroundColor="notificationBackgroundColor"
  />
  <!-- Hero section -->
  <Hero v-bind:cart="cart" @displayCart="displayCart" />
  <Cart
    :showCart="showCart"
    :cart="cart"
    :cartTotal="cartTotal"
    @close-cart="displayCart"
    @check-out="checkOut"
    @remove-from-cart="removeItemFromCart"
  />

  <Product :products="products" v-on:add-cart="addCart" :cart="cart" />
</template>
<script>
import Notification from "../components/Notification";
import Cart from "../components/Cart.vue";
import Hero from "../components/Hero";
import Product from "../components/Products";
export default {
  name: "Home",
  components: {
    Notification,
    Hero,
    Product,
    Cart,
  },
  data() {
    return {
      products: [],
      cart: [], //cart items
      cartTotal: 0, //total cost of items in cart
      showCart: false, //toggle cart display
      notification: "",
      notificationBackgroundColor: "black",
    };
  },
  methods: {
    // add products to cart
    addCart(newProduct) {
      const checkCart = this.cart.every((item) => {
        return item.id != newProduct.id;
      });
      if (checkCart) {
        this.cartTotal =
          this.cartTotal + newProduct.price * newProduct.numberOfItems;
        this.cart = [...this.cart, newProduct];
        // handle notification
        this.notificationBackgroundColor = "black";
        this.notification = "";
        this.notification = `${newProduct.numberOfItems} ${newProduct.name} added to cart`;
        setTimeout(() => (this.notification = ""), 2000);
      } else {
        // handle notification
        this.notificationBackgroundColor = "red";
        this.notification = "";
        this.notification = `Product already in cart`;
        setTimeout(() => (this.notification = ""), 2000);
      }
    },
    // remove products from cart
    removeItemFromCart(id) {
      this.cart = this.cart.filter((item) => {
        item.id === id
          ? (this.cartTotal = this.cartTotal - item.price * item.numberOfItems)
          : "";
        return item.id != id;
      });

      // handle notification
      this.notificationBackgroundColor = "black";
      this.notification = "";
      this.notification = `Item removed form cart`;
      setTimeout(() => (this.notification = ""), 2000);
    },
    // show cart items
    displayCart() {
      this.showCart = !this.showCart;
    },
    // reduceItemsInCart(id) {
    //   this.cart.map((item) => {
    //     if (item.numberOfItems !== 1) {
    //       item.id === id
    //         ? { ...item, numberOfItems: item.numberOfItems-- }
    //         : item;
    //       this.cartTotal = this.cartTotal - item.price;
    //     }
    //   });
    // },
    // increaseItemsInCart(id) {
    //   this.cart.map((item) => {
    //     item.id === id
    //       ? { ...item, numberOfItems: item.numberOfItems++ }
    //       : item;
    //     this.cartTotal = this.cartTotal + item.price;
    //   });
    // },
    // checkout
    checkOut(d) {
      console.log(d);

      setTimeout(() => (this.cart = []), 2000);
    },
  },
  created() {
    this.products = [
      {
        id: 1,
        name: "O.Black Shirt",
        price: 3000,
        img: require("../assets/products/p1.jpg"),
      },
      {
        id: 2,
        name: "W.Blue Shirt",
        price: 2500,
        img: require("../assets/products/p2.jpg"),
      },
      {
        id: 3,
        name: "strip Shirt",
        price: 2500,
        img: require("../assets/products/p3.jpg"),
      },
      {
        id: 4,
        name: "red shirt",
        price: 1500,
        img: require("../assets/products/p4.jpeg"),
      },
      {
        id: 5,
        name: "White Mens",
        price: 3500,
        img: require("../assets/products/p5.jpeg"),
      },
      {
        id: 6,
        name: "Sexy Ladies top",
        price: 2500,
        img: require("../assets/products/p6.jpeg"),
      },
      {
        id: 7,
        name: "Mens Boot",
        price: 2500,
        img: require("../assets/products/p7.jpeg"),
      },
      {
        id: 8,
        name: "Snickers",
        price: 10000,
        img: require("../assets/products/p8.jpeg"),
      },
      {
        id: 9,
        name: "sports",
        price: 12500,
        img: require("../assets/products/p9.jpeg"),
      },
      {
        id: 10,
        name: "LSM",
        price: 5500,
        img: require("../assets/products/p10.jpeg"),
      },
      {
        id: 11,
        name: "Timber Land Women",
        price: 22500,
        img: require("../assets/products/p11.jpeg"),
      },
      {
        id: 12,
        name: "Red Shoes",
        price: 5000,
        img: require("../assets/products/p12.jpeg"),
      },
      {
        id: 13,
        name: "Brown Mens",
        price: 5500,
        img: require("../assets/products/p13.jpg"),
      },
    ];
  },
};
</script>