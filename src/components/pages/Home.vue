<template>
  <Main>
    <div class="container">
      <Todos></Todos>
    </div>
  </Main>
</template>

<script>
import Main from '../layout/Main';
import Todos from '../Todos';

export default {
  name: 'Home',

  components: {
    Main,
    Todos
  }
}
</script>

<style>
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
</style>
