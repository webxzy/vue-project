<template>
  <div class="home">
    <h1>首页</h1>
    <Todo />
  </div>
</template>

<script>

import Todo from './Todo';

export default {
  name: 'home',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  components: {
    Todo
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
