<template>
  <div>
    <p>{{ task.nome }} {{index}}</p>
    <p>{{ task.doDate }}</p>
    <p>{{ task.doTime }}</p>
    <q-btn label="X" @click="deleteTask" />
  </div>
</template>

<script>
export default {
    props:['task', 'index']
};
</script>