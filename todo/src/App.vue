<template>
  <div id="app">{{message}}</div>
</template>

<script>
export default {
  name: 'App',
  components: {},
  data() {
    return {
      message: 'Hello'
    }
  }
}
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}
</style>
