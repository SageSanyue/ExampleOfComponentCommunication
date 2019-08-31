<template>
<div class="footer">
  <slot></slot>
  <p>广告位长期招租哦😯</p>
  <slot  style=”color:yellow;” >这是在slot上添加了样式</slot>
  <p>{{contact}}</p>
  <slot  name=”mySlot”>这是拥有命名的slot的默认内容</slot>
  <join-kind></join-kind>
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
          contact: '800-***-8820'
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
