<template>
<div class="footer">

  <p>广告位长期招租哦😯</p>
  <p>{{contact}}</p>
  <join-kind v-bind="$attrs"></join-kind>

</div>
</template>

<script>
import joinKind from "./kind.vue";

export default {
  name: 'Advertise',
  components: {
      'join-kind': joinKind
  },
  data() {
      return {
          contact: '800-***-8820',
          maneger: 'Tom' // 这个子组件作用域内特有的数据
      }
  },
  props: { a: String }, // a作为props 属性绑定 
  inheritAttrs: false,
  created() {
    console.log('子组件$attrs', this.$attrs)
    console.log('子组件$listeners', this.$listeners)
  },
  methods: {
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.footer {
    width: 300px;
    position: absolute;
    top: 70%;
    left: 50%;
    margin-left: -150px;
}
</style>
