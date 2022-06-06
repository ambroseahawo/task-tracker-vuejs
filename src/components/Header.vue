<template>
  <header>
    <h1>{{ title }}</h1>
    <Button :text="showAddTask ? 'Close': 'Add Task'" @btn-click="$emit('toggle-add-task')"
      :color="showAddTask? 'red': 'green'" 
    />
  </header>
</template>

<script>
import Button from './Button.vue'

export default{
  name: "Header",
  props: {
    title: {
      type: String,
      default: "Default Header"
    },
    showAddTask: Boolean,
  },
  components: {
    Button,
  }
}

</script>


<style>
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
}
</style>