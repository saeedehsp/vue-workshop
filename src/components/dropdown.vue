<template>
  <select name="dropdown" id="dropdown" @change="selectUpdate" v-model="selectedOption">
    <option value="option1"> {{number}} 1  </option>
    <option value="option2"> {{number}} 2 </option>
    <option value="option3"> {{number}} 3 </option>
  </select>
</template>

<script>
export default {
  name: 'dropdown',
  props:{
    number: String
  },
  data() {
    return {
      selectedOption:''
    }
  },
  methods: {
    selectUpdate(){
      this.$emit('update:option',this.selectedOption)
    }
  },
}
</script>
