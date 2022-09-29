<template>
  <header>
    <h1>{{ title }}</h1>
    <Button
      v-show="homePage"
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
    },

    computed: { // computed property --> used for reactivity
      homePage() {
        if(this.$route.path === '/') { // access to this.$route with bunch of methods / this.$router.push() --> redirect
          return true
        } else {
          return false
        }
      }
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
