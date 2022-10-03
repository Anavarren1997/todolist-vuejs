<template>
  <div class="task-container">
    <div class="task-wrapper" :style="{ backgroundColor: taskBackgroundColor }">
      <div class="task">
        <div class="description-container">
          <p>{{ task.description }}</p>
        </div>
        <div class="actions-container">
          <input type="checkbox" v-model="task.finished" />
          <IconDeleteTask
            class="delete-task"
            @click="this.$emit('deleteTask')"
          ></IconDeleteTask>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import IconChevronRight from "./icons/IconChevronRight.vue";
import IconDeleteTask from "./icons/IconDeleteTask.vue";

export default {
  props: {
    task: {
      description: { type: String },
      finished: { type: Boolean },
    },
  },
  components: { IconChevronRight, IconDeleteTask },
  emits: ["deleteTask"],
  computed: {
    taskBackgroundColor: function () {
      return this.task.finished ? "#aeffb3" : "#f4ff91";
    },
  },
};
</script>

<style scooped>
.task-container {
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.task-wrapper {
  width: 80%;
  padding: 10px 15px;
  margin-top: 10px;
  border-radius: 5px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.task {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
  width: 90%;
}

.delete-task {
  height: 24px;
  width: 24px;
  cursor: pointer;
  color: rgb(82, 82, 82);
  transition: 0.2s;
}

.description-container > p {
  font-weight: bold;
}

.delete-task:hover,
.display-subtasks:hover {
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
  cursor: pointer;
}
</style>
