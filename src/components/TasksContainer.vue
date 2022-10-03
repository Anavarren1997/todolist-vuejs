<template>
  <div class="tasks-wrapper">
    <Task
      v-for="task in tasks"
      :task="task"
      @deleteTask="removeTaskFromTasks(task)"
    ></Task>
  </div>
</template>

<script>
import Task from "./Task.vue";
export default {
  props: {
    tasks: { type: Array },
  },
  components: { Task },
  methods: {
    removeTaskFromTasks(task) {
      //Check if task is parent Task. If so, remove
      //Task and subtasks. Otherwise, only remove subtask.
      let taskIndex = this.tasks.indexOf(task);
      this.tasks.splice(taskIndex, 1);
    },
  },
};
</script>

<style scooped>
.tasks-wrapper {
  margin-top: 10px;
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
</style>
