<template>
  <div>
    Filter Todos:
    <select
      @change="
        filterTodos(
          parseInt($event.target.options[$event.target.selectedIndex].innerText)
        )
      "
    >
      <option value="200">200</option>
      <option value="100">100</option>
      <option value="50">50</option>
      <option value="20">20</option>
      <option value="10">10</option>
      <option value="5">5</option>
    </select>
  </div>
</template>

<script>
import { useStore } from 'vuex';

export default {
  name: 'FilterTodos',
  setup() {
    const store = useStore();
    const filterTodos = (length) => store.dispatch('todos/filterTodos', length);
    return {
      filterTodos,
    };
  },
};
</script>

<style>
  select {
    margin-top: 20px;
    padding: 6px;
    border: #41b883 1px solid;
  }
</style>
