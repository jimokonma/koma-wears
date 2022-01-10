<template>
  <div
    class="notification"
    :style="{ backgroundColor: notificationBackgroundColor }"
  >
    <p>{{ notification }}</p>
  </div>
</template>

<script>
export default {
  props: ["notification", "notificationBackgroundColor"],
};
</script>
<style scoped>
.notification {
  width: 100%;
  position: fixed;
  z-index: 99;
  color: white;
  text-align: center;
}
</style>