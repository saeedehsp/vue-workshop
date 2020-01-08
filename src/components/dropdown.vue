<template>
<div>
  <select name="dropdown" id="dropdown" @change="selectUpdate" v-model="selectedOption">
    <option value="option1"> {{number}} 1  </option>
    <option value="option2"> {{number}} 2 </option>
    <option value="option3"> {{number}} 3 </option>
  </select>
  <div> count: {{count}}</div>
</div>
</template>

<script>
export default {
  name: 'dropdown',
  props:{
    number: String,
    count: Number

  },
  data() {
    return {
      selectedOption:'',
      counter: 0
    }
  },
  methods: {
    selectUpdate(){
      this.$emit('update:option',this.selectedOption)
    },
     add(){
     return ++this.count
    }
  },
}
</script>
