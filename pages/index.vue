<template>
  <div class="bg-black h-screen text-white overflow-hidden">
    <div class="w-full lg:w-[500px] mx-auto h-screen py-10 px-4">
      <div class="mb-4">
        <Header :status="showAddTask" @toggle-add-task="toggleAddTask" />
      </div>
      <div v-show="showAddTask">
        <CreateTask @addTask="createNewTask" />
      </div>
      <TasksList @delete-task="handleDelete" :taskslist="taskdata" />
    </div>
  </div>
</template>

<script>
import TasksList from "@/components/TasksList.vue";
export default {
  components: { TasksList },
  data() {
    return {
      taskdata: [],
      showAddTask: true,
    };
  },
  created() {
    this.taskdata = [
      {
        id: 1,
        title: "Bootcamp UI UX Design",
        date: "2023-01-10",
      },
      {
        id: 2,
        title: "Meeting with developer",
        date: "2023-01-10",
      },
    ];
  },
  methods: {
    toggleAddTask() {
      this.showAddTask = !this.showAddTask;
    },
    handleDelete(id) {
      this.taskdata = this.taskdata.filter((task) => task.id !== id);
    },

    createNewTask(newTask) {
      this.taskdata = [...this.taskdata, newTask];
    },
  },
};
</script>
