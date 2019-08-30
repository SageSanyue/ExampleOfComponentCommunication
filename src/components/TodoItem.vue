<template>
<div>
  <span @click="handleTransition">{{realIndex}}</span>
  <li @click="handleClick">{{content}}</li>
</div>
</template>

<script>
export default {
  name: 'TodoItem',
  props: ['content', 'index'],
  computed: {
    realIndex: function() {
      return this.index+1
    }
  },
  methods: {
    handleTransition() {
      alert(this.$parent.title)
    },
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
