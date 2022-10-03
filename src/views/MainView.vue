<template>
  <div class="view-container">
    <TodoContainer> </TodoContainer>
  </div>
</template>

<script>
import TodoContainer from "../components/TodoContainer.vue";
export default {
  components: { TodoContainer },
};
</script>

<style scooped>
.view-container {
  display: grid;
  place-items: center;
  height: 95vh;
}
</style>
