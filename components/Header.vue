<template>
  <div class="flex justify-between">
    <p class="font-bold text-4xl">My Task</p>
    <button
      @click="$emit('toggle-add-task')"
      class="px-4 py-2 rounded bg-blue-500"
    >
      {{ status ? "Hide Text" : "Add New" }}
    </button>
  </div>
</template>

<script>
export default {
  name: "header",
  props: {
    status: Boolean,
  },
};
</script>
