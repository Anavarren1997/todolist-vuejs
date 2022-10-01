<template>
  <div class="view-container">
    <TaskContainer>
    </TaskContainer>
  </div>
</template>

<script>
  import TaskContainer from '../components/TaskContainer.vue'
  export default {
    components: {TaskContainer}
  }
</script>

<style scooped>

  .view-container{
    display: grid;
    place-items: center;
    height: 95vh;
  }

</style>