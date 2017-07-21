<template>
  <div class="todo-list">
    <h2>todo-list</h2>
    <form v-on:submit="submit">
      <input v-model="input" type="text" />
      <button>添加</button>
    </form>
    <ul class="list">
      <li v-for="(item, index) in items" :key="item.id">
        {{item.text}}
        <span v-on:click="remove(item.id)">&times;</span>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'todo',
  data() {
    return {
      input: '',
      items: []
    }
  },
  methods: {
    submit: function (e) {
      e.preventDefault();
      if (this.input.trim() === '') return;
      this.items.push({ id: this.items.length + 1, text: this.input });
      this.input = '';
    },
    remove: function(id) {
      this.items = this.items.filter(item => item.id !== id);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.list span {
  cursor: pointer;
  color: red;
}
</style>