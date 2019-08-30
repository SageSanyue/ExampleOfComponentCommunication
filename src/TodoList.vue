<template>
  <div id="app">
    <h1>Todo-list</h1>
    <input v-model="inputValue" type="text">
    <button @click="handleSubmit">提交</button>
    <todo-item 
      v-for="(item, index) of list" 
      :key="index"
      :content="item"
      :index="index"
      @delete="handleDelete"
    >
    </todo-item>
    <div>
      <button @click="handleChild">点我可以获取item第2条的值</button>
    </div>
  </div>
</template>

<script>
import TodoItem from './components/TodoItem.vue'

export default {
  name: 'TodoList',
  components: {
    'todo-item': TodoItem
  },
  data() {
    return {
      inputValue: '',
      list: []
    }
  },
  methods: {
    handleChild() {
      // 获取子组件todo-item指定某项的值
      console.log(this.$children[1].realIndex)
    },
    handleSubmit() {
      this.list.push(this.inputValue)
      this.inputValue = ''
    },
    handleDelete(index) {
      this.list.splice(index, 1)
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
