<template>
  <div id="app">
    <h1>slot</h1>
    <!-- use the slot method to import additional content in slot_test components -->
    <slot-test>
      <!-- 這是不具名的插槽 (slot), name: default -->
      {{content}}
      <br>
      name from arrayData: {{arrayData[0].name}}
    </slot-test>

    <!-- default custom button -->
    <submit-button></submit-button>
    <submit-button>
      <!-- Here is another example to use a slot method for the button . -->
      {{'This is another button name.'}}
    </submit-button>

    <hr>
    <h1>named-slot</h1>
    <named-slot>
      <!-- 
        named slot use template, slot or v-slot (or shorthand #) 
        to insert content into specify area.
        p.s. 
          1. v-slot support after version 2.6.0, and only be added to a <template>
          2. slot  support before version 2.6.0 
      -->
      <template slot="header">
        <h3>This is a slot content in header:</h3>
        <p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Fuga reprehenderit tenetur magnam nemo quam veritatis vero commodi recusandae, debitis excepturi facilis culpa mollitia modi voluptatem vel expedita iste pariatur quaerat.</p>
      </template>
      <template v-slot:section>
        <h3>This is a slot content in section:</h3>
        <p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Fuga reprehenderit tenetur magnam nemo quam veritatis vero commodi recusandae, debitis excepturi facilis culpa mollitia modi voluptatem vel expedita iste pariatur quaerat.</p>
      </template>
      <template #footer>
        <h3>This is a slot content in footer:</h3>
        <p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Fuga reprehenderit tenetur magnam nemo quam veritatis vero commodi recusandae, debitis excepturi facilis culpa mollitia modi voluptatem vel expedita iste pariatur quaerat.</p>
      </template>
    </named-slot>

    <hr>
    <h1>scoped-slot</h1>
    <scoped-slot>
      <!-- 
        Target: use children component's data to replace text in parent component.
        Step1: (In custom component tag) use slot and slot-scope or v-slot
          1. use slot and slot-scope
          2. use v-slot 
        Step2: (In children component) bind the data which we want to use in children component.
      -->
      <template slot="header" slot-scope="props">
        {{props.testAry[1].text2}}
      </template>
      <template #section="{testAry}">
        {{testAry[1].text2}}
      </template>
      <template #footer="{testAry, testAry2}">
        <!-- destructuring slot props:
          we can use mustache to destructuring slots when we have to get much data to use
        -->
        <p>{{testAry[1].text2}}</p>
        <p>{{testAry2[1].text2}}</p>
      </template>
    </scoped-slot>
  </div>
</template>


<script>
import slot_test from '@/components/slot_test.vue';
import submitButton from '@/components/button.vue';
import namedSlot from '@/components/named_slot.vue';
import scopedSlot from '@/components/scoped_slot.vue';

export default {
  data() {
    return {
      content: 'This is a content due to slot method.',
      arrayData: [{name: 'Penghua'}],
    }
  },
  components: {
    "slot-test": slot_test,
    "submit-button": submitButton,
    "named-slot":namedSlot,
    "scoped-slot": scopedSlot
  }
}
</script>
<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
