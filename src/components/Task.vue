<template>
  <div class="task-wrapper" :style="{ backgroundColor: taskBackgroundColor }">
    <div class="task-container">
      <div class="description-container">
        <p>{{ task.description }}</p>
      </div>
      <div class="actions-container">
        <input type="checkbox" v-model="task.finished" />
        <IconDeleteTask class="delete-task"></IconDeleteTask>
      </div>
    </div>
    <div class="display-subtasks-container">
      <IconChevronRight class="display-subtasks"></IconChevronRight>
    </div>
  </div>
</template>

<script>
import IconChevronRight from "./icons/IconChevronRight.vue";
import IconDeleteTask from "./icons/IconDeleteTask.vue";

export default {
  props: {
    task: {},
  },
  components: { IconChevronRight, IconDeleteTask },
  computed: {
    taskBackgroundColor: function () {
      return this.task.finished ? "#aeffb3" : "#f4ff91";
    },
  },
};
</script>

<style scooped>
.task-wrapper {
  width: 80%;
  padding: 10px 15px;
  margin-top: 10px;
  border-radius: 5px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.task-container {
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

.display-subtasks {
  display: grid;
  place-content: center;
  cursor: pointer;
  color: rgb(82, 82, 82);
  height: 16px;
  width: 16px;
}
</style>
