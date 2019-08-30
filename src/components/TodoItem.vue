<template>
  <li @click="handleClick">{{content}}</li>
</template>

<script>
export default {
  name: 'TodoItem',
  props: ['content', 'index'],
  methods: {
    handleClick() {
      this.$emit('delete', this.index)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
li {
  color: yellowgreen;
}
</style>
