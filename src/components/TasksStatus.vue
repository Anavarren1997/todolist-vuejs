<template>
  <div class="tasks-status">
    <p class="total">Total: {{ tasks.length }}</p>
    <p class="done">Done: {{ finishedTasks }}</p>
    <p class="pending">Pending: {{ tasks.length - finishedTasks }}</p>
  </div>
  <div class="underline-tasks-status"></div>
</template>

<script>
export default {
  props: {
    tasks: {type: Array},
  },
  computed: {
    finishedTasks: function () {
      let count = 0;
      this.tasks.forEach((t) => {
        if (t.finished) count++;
      });
      return count;
    },
  },
};
</script>

<style scooped>
.tasks-status {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  width: 80%;
}

.underline-tasks-status{
  width: 80%;
  margin-top: 20px;
  border-bottom: 1px solid;
  color: rgb(82, 82, 82);
}

.tasks-status>p {
    padding: 4px 15px;
    font-weight: bolder;
    border-radius: 5px;
}

.total{
    background-color: rgb(211, 196, 254);
    color: rgb(70, 42, 149);
}

.done {
    background-color: rgb(174, 255, 179);
    color: rgb(22, 111, 27);
}

.pending{
    background-color: rgb(244, 255, 145);
    color: rgb(103, 111, 29);
}

</style>
