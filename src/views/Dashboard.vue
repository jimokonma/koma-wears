<template>
  <div class="dashboard">
    <SideNav />
    <div class="dashboard-body">
      <nav>
        <h1>Dashboard</h1>
        <router-link to="/">View site</router-link>
      </nav>
      <div class="container">
        <div class="data-container">
          <div class="big-container">
            <div class="title">
              <h3>Monthly Statistics</h3>
            </div>
            <div class="chart"></div>
            <div class="summary">
              <li>
                <p>Total Orders</p>
                <p>150</p>
              </li>
              <li>
                <p>Pending Orders</p>
                <p>46</p>
              </li>
              <li>
                <p>Total Sales</p>
                <p>21m</p>
              </li>
            </div>
          </div>
        </div>
        <div class="data-container">
          <div class="small-container">
            <div class="title">
              <h3>Total Sales</h3>
              <p>last 7 days</p>
            </div>
            <div class="total-sale">
              <h1>N480k</h1>
              <p>2,450</p>
            </div>
          </div>
          <div class="small-container">
            <div class="title">
              <h3>Total Sales</h3>
              <p>last 7 days</p>
            </div>
          </div>
        </div>
        <div class="data-container">
          <div class="big-container">
            <div class="title">
              <h3>Total Orders</h3>
              <p>last 7 days</p>
            </div>
            <div class="chart"></div>
            <div class="summary">
              <li>
                <span>
                  <div class="circle" style="background: #f5c57c"></div>
                  <p>Pending</p>
                </span>

                <p>10 / 55%</p>
              </li>
              <li>
                <span>
                  <div class="circle" style="background: #8cf57c"></div>
                  <p>Processing</p>
                </span>
                <p>2/11.1%</p>
              </li>
              <li>
                <span>
                  <div class="circle" style="background: #f57cac"></div>
                  <p>On hold</p>
                </span>
                <p>0 / 0%</p>
              </li>
              <li>
                <span>
                  <div class="circle" style="background: #7c84f5"></div>
                  <p>Completed</p></span
                >
                <p>5 / 27.8%</p>
              </li>
              <li>
                <span>
                  <div class="circle" style="background: #f57c7c"></div>
                  <p>Cancled</p></span
                >
                <p>1 / 5.6%</p>
              </li>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import SideNav from "../components/dashboard/SideNav.vue";
export default {
  name: "Dashboard",
  components: { SideNav },
  data() {
    return {
      datacollection: null,
      loaded: false,
    };
  },
  mounted() {
    this.fillData();
  },
  methods: {
    fillData() {
      this.datacollection = {
        labels: ["1", "2", "3", "4"],
        datasets: [
          {
            label: "numbers",
            backgroundColor: "#f87979",
            data: [40, 10, 8, 20],
          },
        ],
      };
      console.log(this.datacollection);
    },
  },
};
</script>
<style scoped>
.dashboard {
  display: flex;
  position: relative;
  background: #ebebeb;
}
.dashboard-body {
  width: 100%;
}
nav {
  height: 50px;
  display: flex;
  justify-content: space-evenly;
  align-items: center;
  background: #9dc79f;
}
.container {
  width: 100%;
  height: 300x;
  display: flex;
  justify-content: space-evenly;
  align-items: center;
  flex-wrap: wrap;
}
.data-container {
  height: 350px;
  flex: 1;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  margin: 5px;
}
.small-container {
  height: 150px;
  padding: 10px;
  background: rgb(255, 255, 255);
}
.big-container {
  height: 100%;
  padding: 10px;
  background: rgb(255, 255, 255);
}
.title h3 {
  font-size: 12px;
  color: #bebebe;
}
.title p {
  font-size: 9px;
  font-style: italic;
  color: #bebebe;
}
.summary {
  width: 150px;
  margin: 0px auto;
  font-size: 10px;
  color: #5e5e5e;
  list-style: none;
}
.summary li {
  display: flex;
  justify-content: space-between;
  margin: 10px 0px;
}
.summary li span {
  display: flex;
}
.circle {
  width: 5px;
  height: 5px;
  margin-right: 5px;
  border-radius: 100%;
}
.total-sale h1,
.total-sale p {
  text-align: center;
}
.total-sale {
  margin-top: 30px;
}
.total-sale h1 {
  border-bottom: 1px solid #ebebeb;
}
.total-sale p {
  font-size: small;
  color: green;
}
</style>