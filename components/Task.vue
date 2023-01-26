<template>
  <div class="bg-gray-800 p-4 flex justify-between items-center">
    <div>
      <p>{{ task.title }}</p>
      <p class="text-slate-400 text-sm">{{ task.date }}</p>
    </div>
    <button class="bg-red-500 px-2 py-2" @click="$emit('on-click', task.id)">
      Delete
    </button>
  </div>
</template>

<script>
export default {
  props: {
    task: Object,
  },
};
</script>
