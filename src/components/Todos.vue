<template>
  <section class="container mx-auto">
    <h1 class="text-center text-6xl">Todos</h1>
    <section v-for="todo in this.todos" :key="todo.id">
      <Todo :todo="todo" @delete-item="deleteItem"/>
    </section> 
    <AddTodo @add-todo="addTodo"/>
  </section>
</template>

<script>
import Todo from './Todo';
import AddTodo from './AddTodo';
export default {
  name: 'Todos',
  components: {
    Todo,
    AddTodo
  },
  methods: {
    deleteItem(id) {
      this.todos = this.todos.filter(todo => todo.id != id);
    },
    addTodo(todo){
      this.todos.push(todo);
    }
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: 'Fix Bug',
          completed: true 
        },
        {
          id: 2,
          title: 'Add Decouvert feature',
          completed: false
        },
        {
          id: 3,
          title: 'Add Taxe for Frequence',
          completed: false
        }
      ]
    }
  },
 
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
section{
    width: 500px;
    margin: auto;
}
</style>
