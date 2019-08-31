<template>
<div class="footer">
  <slot name="header"></slot>

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
