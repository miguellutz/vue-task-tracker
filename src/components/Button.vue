<template>
  <button @click="onClick()" :style="{background: color}"
  class="btn">{{ text }}</button> <!-- v-on:click="onClick()" -->
</template>

<script>
  export default {
    // eslint-disable-next-line vue/multi-word-component-names
    name: 'Button',

    props: {
      text: String,
      color: String
    },

    methods: {
      onClick() {
        this.$emit('btn-click')
      }
    }
  }

</script>
