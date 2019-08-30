<template>
<div>
  <span>{{realIndex}}</span>
  <li @click="handleClick">{{content}}</li>
</div>
</template>

<script>
export default {
  name: 'TodoItem',
  props: ['content', 'index'],
  data() {
    return {
      message: '待办'
    }
  },
  computed: {
    realIndex: function() {
      return this.index+1
    }
  },
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
