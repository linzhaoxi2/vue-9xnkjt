<template>
  <div class="child-view">
    <p>儿子组件</p>
    {{row2}}
    <GrandChild v-bind="$attrs"></GrandChild>
  </div>
</template>

<script>
import GrandChild from './test2.vue';

export default {
  // 继承所有父组件的内容
  inheritAttrs: true,
  props: {
    row2: {
      type: Object,
      dedault: () => {},
    },
  },
  components: { GrandChild },
  data() {
    return {};
  },
};
</script>
