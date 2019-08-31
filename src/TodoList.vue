<template>
  <div id="app">
    <h1>{{title}}</h1>
    <input v-model="inputValue" type="text">
    <button @click="handleSubmit">提交</button>
    <todo-item
      ref="childrenItems"
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
    <advertise>
      <span style="color:blue;">猜猜我啥颜色</span>
    </advertise>
  </div>
</template>

<script>
import TodoItem from './components/TodoItem.vue'
import Advertise from './components/advertise.vue'

export default {
  name: 'TodoList',
  data() {
    return {
      title: 'Todo-list',
      inputValue: '',
      list: []
    }
  },
  updated() {
    var childrenItems = this.$refs.childrenItems
    console.log(childrenItems)
  },
  components: {
    'todo-item': TodoItem,
    'advertise': Advertise
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
