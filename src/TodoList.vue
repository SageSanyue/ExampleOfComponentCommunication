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

    <div class="event-bus-ex">
      <show-num-com></show-num-com>
      <addition-num-com></addition-num-com>
    </div>

    <advertise
      :title="title"
      :a="a"
      :b="b"
      :c="c"
      @two="triggerTwo"
    >
    </advertise>
  </div>
</template>

<script>
import TodoItem from './components/TodoItem.vue'
import Advertise from './components/advertise.vue'
import showNumCom from './components/showNum.vue'
import additionNumCom from './components/additionNum.vue'

export default {
  name: 'TodoList',
  components: {
    'todo-item': TodoItem,
    'advertise': Advertise,
    'show-num-com': showNumCom, 
    'addition-num-com': additionNumCom
  },
  data() {
    return {
      title: 'Todo-list',
      inputValue: '',
      list: [],
      a: 'aa',
      b: 'bb',
      c: 'cc'
    }
  },
  methods: {
    triggerTwo () {
      console.log('two')
    },
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
  },
  updated() {
    var childrenItems = this.$refs.childrenItems
    console.log(childrenItems)
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
.event-bus-ex {
  position: absolute;
  top: 50%;
  left: 74%
}
</style>
