<template>
  <div class="container">
    <header >
      <h2>This is a header.</h2>
      <slot name="header"></slot>
    </header>
    <section>
      <h2>This is a section.</h2>
      <slot name="section"></slot>
    </section>
    <footer>
      <h2>This is a footer.</h2>
      <slot name="footer"></slot>
    </footer>
  </div>
</template>

<script>
export default {
  data() {
    return {
    }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
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
  color: #42b983;
}

</style>
