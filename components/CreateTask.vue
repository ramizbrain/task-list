<template>
  <!-- Create New Post -->
  <div class="">
    <form @submit.prevent="onSubmit">
      <label class="flex flex-col">
        Title:
        <input
          class="border text-black p-2 rounded-md"
          v-model="title"
          placeholder="Task"
          type="text"
        />
      </label>
      <br />
      <label class="flex flex-col">
        Date:
        <input
          class="text-black p-2 rounded-md"
          v-model="date"
          type="date"
          id="start"
          name="trip-start"
        />
      </label>
      <br />
      <button
        class="bg-blue-500 font-medium py-2 px-4 rounded-lg"
        type="submit"
      >
        Add Task
      </button>
    </form>
  </div>
</template>

<script>
export default {
  name: "create-task",
  data() {
    return {
      id: "",
      title: "",
      date: "",
    };
  },
  methods: {
    onSubmit() {
      if (!this.title || !this.date) {
        alert("isi data dengan benar");
        return;
      }

      const newTask = {
        id: Math.floor(Math.random() * 1000),
        title: this.title,
        date: this.date,
      };

      this.$emit("addTask", newTask);

      this.id = "";
      this.title = "";
      this.date = "";
    },
  },
};
</script>
