<template>
  <div class="side-nav">
    <header>
      <img :src="logo" alt="" class="logo" />
    </header>
    <div class="user-profile">
      <img :src="icons.profile" alt="user profile" />
      <span>
        <h3>Username</h3>
        <p>Lorem ipsum dolor sit amet consectetur</p>
      </span>
    </div>
    <nav>
      <ul>
        <li>
          <p><img :src="icons.analysis" alt="dashboard" /> Dashboard</p>
        </li>
        <li>
          <p><img :src="icons.cart" alt="dashboard" /> Orders</p>
          <p class="order-count">49</p>
        </li>
        <li>
          <p><img :src="icons.shopingBag" alt="products" /> Products</p>
        </li>
        <li>
          <p><img :src="icons.analysis" alt="analysis" /> Analysis</p>
        </li>
        <li>
          <p><img :src="icons.user" alt="user" /> Users</p>
        </li>
      </ul>
    </nav>
  </div>
</template>
<script>
export default {
  name: "SideNav",
  data() {
    return {
      logo: require("../../assets/logo.png"),
      icons: {
        analysis: require("../../assets/icons/analysis-icon.svg"),
        cart: require("../../assets/icons/cart-icon.svg"),
        shopingBag: require("../../assets/icons/shoping-bag-icon.svg"),
        user: require("../../assets/icons/user-icon.svg"),
        profile: require("../../assets/icons/user-profile-icon.svg"),
      },
    };
  },
};
</script>
<style scoped>
/* Side navbar and components */
.side-nav {
  width: 35vw;
  max-width: 200px;
  height: 100vh auto;
  padding: 15px;
  background: #ffffff;
}
.user-profile {
  display: flex;
  padding: 20px 0px;
}
.user-profile img {
  width: 30px;
}
.user-profile h3 {
  font-size: 12px;
}
.user-profile span {
  margin-left: 15px;
}
.user-profile span p {
  font-size: 10px;
  color: #5e5e5e;
}
nav ul {
  list-style: none;
}
nav li {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 15px 0px;
  border-bottom: 1px solid #dcdcdc;
}
.order-count {
  color: white;
  background: #9dc79f;
  border-radius: 50%;
  padding: 3px;
}
nav li p {
  display: flex;
  align-items: center;
  justify-content: space-between;
  font-size: 10px;

  color: #5e5e5e;
}
nav li p img {
  width: 15px;
  margin-right: 10px;
}
</style>