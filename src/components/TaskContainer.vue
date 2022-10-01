<template>
  <div class="todo-container">
    <InputTask @taskAdded="tasks.push($event)"></InputTask>
    <TasksStatus :tasks="tasks"></TasksStatus>
    <div class="task-wrapper">
      <Task
        v-for="task in tasks"
        :task="task"
        @deleteTask="removeTaskFromTasks(task)"
      ></Task>
    </div>
  </div>
</template>

<script>
import InputTask from "./InputTask.vue";
import Task from "./Task.vue";
import TasksStatus from "./TasksStatus.vue";

export default {
  components: { InputTask, Task, TasksStatus },
  data() {
    return {
      tasks: [],
    };
  },
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
.todo-container {
  height: 60vh;
  width: 45vw;
  min-height: 500px;
  min-width: 650px;
  background-color: white;
  border-radius: 15px;
  box-shadow: rgba(99, 99, 99, 0.2) 0px 3px 10px 0px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: start;
}

.task-wrapper{
  margin-top: 10px;
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

</style>
