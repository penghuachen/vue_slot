<template>
  <div class="hello">
    <h1>This is a title.</h1>
    <!-- Here's slot mapping content and arrayData-->
    <!-- 
        if slot get nothing , it will use default value. Here is "This is a content"  
        (can comment out content, arrayData to observe)
    -->
    <slot>This is a content</slot>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Maiores maxime possimus dolorem voluptatem! Provident architecto vero nobis optio omnis vitae quaerat maxime error sapiente, sit a explicabo laborum perspiciatis obcaecati.</p>
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
</style>
