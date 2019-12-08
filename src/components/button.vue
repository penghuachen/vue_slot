<template>
  <div class="btn">
    <button>
      <slot>This is default button name.</slot>
    </button>
  </div>
</template>

<script>
export default {}
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

.btn {
  button {
    line-height: 25px;
    margin: 0 auto;
    border-radius: 4px;
    margin-bottom: 15px;
  }
}
</style>
