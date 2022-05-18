<template>
  <nav style="display: flex">
    <router-link to="/z-header">Home</router-link>
    <router-link to="/z-body">CAD</router-link>
    <router-link to="/z-modulo-x">Modulo x</router-link>
  </nav>
  <router-view/>
</template>

<script>
export default {
  
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;
    margin: 10px;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
