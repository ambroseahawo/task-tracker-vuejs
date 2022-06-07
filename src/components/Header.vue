<template>
  <header>
    <h1>{{ title }}</h1>
    <Button v-show="homepage" :text="showAddTask ? 'Close': 'Add Task'" 
      @btn-click="$emit('toggle-add-task')"
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
  },
  computed: {
    homepage(){
      if(this.$route.path === '/'){
        return true
      } else{
        return false
      }
    }
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