<template>
  <div class="space-y-4 mt-4">
    <div v-for="task in taskslist" :key="task.id">
      <Task @on-click="$emit('delete-task', task.id)" :task="task" />
    </div>
  </div>
</template>

<script>
export default {
  props: {
    taskslist: Array,
  },
  emits: ["delete-task"],
};
</script>
