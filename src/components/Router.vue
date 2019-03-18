<template>
  <component :is="routedComponent"></component>
</template>

<script>
import Home from "./pages/Home";
import About from "./pages/About";

const routes = {
  "/": Home,
  "/about": About
};

export default {
  data() {
    return { current: window.location.pathname };
  },
  computed: {
    routedComponent() {
      return routes[this.current];
    }
  }
};
</script>