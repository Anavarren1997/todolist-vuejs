<template>
  <div class="input-wrapper">
    <div class="input-container">
      <div class="text-container">
        <input class="input" type="text" placeholder="Add a Task..." v-model="newTask" />
      </div>
      <div class="button-container">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          viewBox="0 0 24 24"
          stroke-width="1.5"
          stroke="currentColor"
          class="w-6 h-6 button-add-task"
          @click="addTask()"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M12 9v6m3-3H9m12 0a9 9 0 11-18 0 9 9 0 0118 0z"
          />
        </svg>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newTask: "",
    };
  },
  methods: {
    addTask() {
      this.$emit("taskAdded", {
        description: this.newTask,
        priority: "",
        finished: false,
        subTasks: [],
      });
      this.newTask = "";
    },
  },
};
</script>

<style scooped>
.input-wrapper {
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
}

.input-container {
  width: 45%;
  height: 45px;
  margin: 15px 0;
  border: 1px solid #ccc;
  border-radius: 25px;
  box-sizing: border-box;
  transition: width 0.4s ease-in-out;
  display: flex;
  align-items: center;
  justify-content: center;
}

.text-container {
  width: 80%;
  height: 100%;
  display: flex;
  align-items: center;
}

.input {
  height: 100%;
  width: 100%;
  border: none;
  background-color: transparent;
}

.input:focus {
  outline: none;
}

.button-container {
  width: 10%;
  display: flex;
  align-items: center;
  justify-content: flex-end;
}

.button-add-task {
  height: 24px;
  width: 24px;
  color: rgb(82, 82, 82);
  cursor: pointer;
  transition: 0.2s;
}

.button-add-task:hover {
  height: 26px;
  width: 26px;
  color: rgb(20, 20, 20);
}
</style>
