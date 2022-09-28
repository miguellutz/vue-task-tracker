<template>
  <header>
    <h1>{{ title }}</h1>
    <Button
      @btn-click="$emit('toggle-add-task')"
      :text="showAddTask ? 'Close' : 'Add Task'"
      :color="showAddTask ? 'red' : 'green'"
    />
  </header>
</template>

<script>
  import Button from './Button'

  export default {
    // eslint-disable-next-line vue/multi-word-component-names
    name: 'Header',
    // props: ['title'] --> props can be specified as an array or as an object with type
    props: {
      title: {
        type: String,
        default: 'Hello World',
      },
      showAddTask: Boolean
    },

    components: {
      Button
    }
  }
</script>

<style scoped>
  header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 20px;
  }
</style>
