<template>
  <div id="app">
      <p>Hello world</p>
  </div>
</template>

<script>

export default {
  name: 'App',
  components: {

  },
  data() {
      return {
          todos: [
              {
                  id: 1,
                  title: 'one',
                  completed: false
              },
              {
                  id: 2,
                  title: 'two',
                  completed: true
              },
              {
                  id: 3,
                  title: 'three',
                  completed: false
              }
          ]
      }
  }
}
</script>

<style>
*{
    padding: 0;
    margin: 0;
}

body {
    font-family: Arial, Helvetica, sans-serif;
    line-height: 1.4;
}
</style>
