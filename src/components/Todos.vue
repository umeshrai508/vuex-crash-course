<template>
  <div>
    <h3>Todos</h3>
    <div class="todos">
      <div v-for="todo in allTodos" :key="todo.id" class="todo">
        {{ todo.title }}
        <i class="fas fa-trash-alt" @click="deleteTodo(todo.id)" />
      </div>
    </div>
  </div>
</template>


<script>
import { mapGetters, mapActions } from "vuex";
console.log(mapGetters);
export default {
  name: "Todos",
  computed: mapGetters(["allTodos"]),
  methods: { ...mapActions(["fetchTodos", "deleteTodo"]) },
  created() {
    this.fetchTodos();
  },
};
</script>

<style scoped>
.todos {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1rem;
}
.todo {
  border: 1px solid #ccc;
  background: #41b883;
  padding: 1rem;
  border-radius: 5px;
  text-align: center;
  position: relative;
  cursor: pointer;
}
i {
  position: absolute;
  bottom: 10px;
  right: 10px;
  color: #ffffff;
  cursor: pointer;
}
</style>>

