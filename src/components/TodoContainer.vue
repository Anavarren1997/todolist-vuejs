<template>
  <div class="todo-container">
    <InputTask @taskAdded="tasks.push($event)"></InputTask>
    <TasksStatus :tasks="tasks"></TasksStatus>
    <TasksContainer :tasks="tasks"></TasksContainer>
  </div>
</template>

<script>
import InputTask from "./InputTask.vue";
import TasksStatus from "./TasksStatus.vue";
import TasksContainer from "./TasksContainer.vue";

export default {
  components: { InputTask, TasksStatus, TasksContainer },
  data() {
    return {
      tasks: [],
    };
  },
};
</script>

<style scooped>
.todo-container {
  height: 60vh;
  width: 40vw;
  min-height: 500px;
  min-width: 650px;
  background-color: white;
  border-radius: 15px;
  box-shadow: rgba(99, 99, 99, 0.2) 0px 3px 10px 0px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: start;
  overflow-y: auto;
}
</style>
