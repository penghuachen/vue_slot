<template>
  <div class="container">
    <header >
      <h2>This is a header.</h2>
      <slot name="header" :testAry="testAry">
        {{testAry[0].text}}
      </slot>
    </header>
    <section>
      <h2>This is a section.</h2>
      <slot name="section" :testAry="testAry"></slot>
    </section>
    <footer>
      <h2>This is a footer.</h2>
      <slot name="footer" :testAry="testAry" :testAry2="testAry2">
        <p>{{testAry[0].text}}</p>
        <p>{{testAry2[0].text}}</p>
      </slot>
    </footer>
  </div>
</template>

<script>
export default {
  data() {
    return {
      testAry: [
        {text: 'This is a text.'},
        {text2: 'This is a text2.'}
      ],
      testAry2: [
        {text: 'This is another text.'},
        {text2: 'This is another text2.'}
      ],
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
