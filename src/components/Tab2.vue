<template>
  <div id="Tab2">
    <h1>{{ msg }}</h1>
    <label for="checkbox">Checkbox:</label>
    <input type="checkbox" id="checkbox"/>
  </div>
</template>

<script>
  export default {
    name: 'Tab2',
    data() {
      return {
        msg: "I am Tab2"
      }
    }
  }
</script>

<style scoped>

</style>
