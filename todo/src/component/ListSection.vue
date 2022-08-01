<script setup>
const props = defineProps({
  listTodo: Array,
});
</script>

<template>
  <div>
    <table>
      <thead>
        <th>Check</th>
        <th>Id</th>
        <th>Name</th>
        <th>Completed</th>
      </thead>
      <tbody>
        <tr v-for="item in props.listTodo" :key="item.id">
          <td><input v-model="props.listTodo.completed" type="checkbox"></td>
          <td>{{item.id}}</td>
          <td>{{item.name}}</td>
          <td>{{item.completed}}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<style scoped>
  table{
    width: 100%;
  }
  th{
    text-align: left;
  }
  thead{
    background: #b0b0b0;
  }
  tr:nth-child(even){
    background: #efefef;
  }
</style>
