<template>
  <div class="task-container">
    <div class="description-container">
      <p>{{ task.description }}</p>
    </div>
    <div class="actions-container">
      <input type="checkbox" v-model="task.finished"/>
      <svg
        xmlns="http://www.w3.org/2000/svg"
        fill="none"
        viewBox="0 0 24 24"
        stroke-width="1.5"
        stroke="currentColor"
        class="w-6 h-6 delete-task"
        @click="this.$emit('deleteTask')"
      >
        <path
          stroke-linecap="round"
          stroke-linejoin="round"
          d="M15 12H9m12 0a9 9 0 11-18 0 9 9 0 0118 0z"
        />
      </svg>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    type: "", //could be either main task or subtask
    task: {},
  },
};
</script>

<style scooped>
.task-container {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
  width: 75%;
  margin-top: 10px;
}

.delete-task {
  height: 24px;
  width: 24px;
  cursor: pointer;
  color: rgb(82, 82, 82);
  transition: 0.2s;
}

.delete-task:hover {

  color: rgb(20, 20, 20);
}

.actions-container {
  display: flex;
  align-items: center;
}

.actions-container > input {
  margin-right: 15px;
  width: 16px;
  height: 16px;
  border-width: 3px;
}
</style>
