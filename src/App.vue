<template>
  <div id="app">
    <img src="./assets/logo.svg">
    <router-view></router-view>
  </div>
</template>

<script>
export default {
  name: 'app',
};
</script>

<style>
body {
  background: url('~@/assets/images/bg.png');
}
</style>
