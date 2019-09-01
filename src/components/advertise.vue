<template>
<div class="footer">
  <slot name="header"></slot>

  <slot name="someNew" v-bind:person="maneger"></slot>
  <!-- <slot name="someNew" :person="maneger"></slot> -->

  <slot></slot>

  <p>广告位长期招租哦😯</p>
  <p>{{contact}}</p>
  <join-kind></join-kind>

  <slot name="haha"></slot>
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
