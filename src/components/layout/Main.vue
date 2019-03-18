<template>
  <div id="app">
    <Navigation />
    <slot></slot>
  </div>
</template>

<script>
import Navigation from './Navigation';

export default {
    name: "Main",

    components: {
      Navigation
    }
}
</script>

<style scoped>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  line-height: 1.4;
}
.container {
  max-width: 700px;
  margin: 0 auto;
}
.btn {
  display: inline-block;
  border:none;
  background: #555;
  color:#FFF;
  padding:7px 20px;
  cursor: pointer;
}
.btn:hover {
  background:#666;
}
</style>