/* eslint-disable vue/require-v-for-key */
<template>
  <div id="app">


    <div class="section">
      <div class="title"> reactivity and data-binding: </div>
      <div >{{message}}</div>
      <input type="text" v-model="message" placeholder="input">
    </div>
    <!-- event handling -->
    <div class="section">
      <div class="title"> event handling:</div>
      <div>  counter: {{counter}}</div>
      <button @click="counter++">plus</button>
    </div>
    <!-- conditional rendering -->
    <div class="section">
      <div class="title"> conditional rendering:</div>
      <div v-if="type === 'b'">type is b</div>
      <div v-else>not b</div>
    </div>
    <!-- list rendering -->
    <div class="section">
      <div class="title"> list rendering:</div>
      <div>  items:</div>
      <div v-for="item in items" :key="item.id">
        {{item.name}}
      </div>
    </div>

    <!-- computed properties -->
    <div class="section">
      <div class="title">computed properties:</div>
      <div> price: {{price}} </div>
      <div> tax: {{tax}}</div>
    </div>
    <!-- component example -->
    <div class="section">
      <div class="title"> component example:</div>
      <dropdown @update:option="option" number="option"></dropdown>
    </div>
  </div>
</template>

<script>
import dropdown from './components/dropdown.vue'

export default {
  name: 'app',
  components:{
    dropdown
  },
  data() {
    return {
      message:'',
      counter: 0,
      items:[{
          id:0,
          name: 'book'},
        {
          id:1,
         name: 'video'
        },
        {
          id:2,
          name: 'game'
      }],
      type: 'a',
      price : 200,
      item: ''
    }
  },
  methods: {
    option(value){
      // eslint-disable-next-line no-console
      console.log(value)
    }
  },
  computed: {
    tax(){
      return this.price * 0.1
    }
  },
}
</script>

<style>
#app {
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.section{
  margin: 2% 0 2% 0
}
.title{
  color: #16693b;
}
</style>
