// showNum.vue 中接收事件

<template>
  <div>计算和: {{count}}</div>
</template>

<script>
import {EventBus} from '../common/eventBus.js'

export default {
  data() {
    return {
      count: 0
    }
  },

  mounted() {
    EventBus.$on('addition', param => {
      console.log('param', param)
      this.count = this.count + param.num;
      console.log('EventBus', EventBus)
    })
  }
}
</script>