<template>
<div class="kind">
    <span>请选择租位类型：</span>
    <select name="租位类型" id="type" v-model="chooseValue" placeholder="请选择">
        <option 
          v-for="(item, index) of chooseType" 
          :value="item"
          :key="index"
          :label="item"
        >
        </option>
    </select>
</div>
</template>

<script>
export default {
  name: 'joinKind',
  inheritAttrs: false, // 可以关闭自动挂载到组件根元素上的没有在props声明的属性
  data() {
      return {
          chooseType: [
              '一周',
              '包月',
              '包季', 
              '包年'
          ],
          chooseValue: ''
      }
  },
  created() {
    console.log('孙组件$attrs', this.$attrs)
    this.$listeners.two()
  },
  methods: {
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.kind {
    color:turquoise;
}
</style>
