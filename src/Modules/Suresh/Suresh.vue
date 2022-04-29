<script>
  export default {
    data(){
      return {
        count: 0,
      }
    }
  }
</script>

<template>
  <h1>This is my interface ( Suresh )</h1>
  <p>Count : <span v-html="count"></span></p>
  <button @click="count++">Increment</button>
</template>