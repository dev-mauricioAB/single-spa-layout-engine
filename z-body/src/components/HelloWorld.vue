<template>
  <div class="hello">
    <h1>z-Body</h1>
    <button type="button" @click="goTo('/z-header')">CAD</button>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  methods: {
    goTo(path){
      console.log(path)

      // dispatchEvent(new CustomEvent(
      //   '@zitrus/z-body/goToRoute',
      //   {
      //     detail: {
      //       path: path
      //     }
      //   }
      // ))
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #005f33;
}
</style>
