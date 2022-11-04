<template>
  <div>
    <button @click="transmitClick">213213</button>

    <!-- 儿子组件 -->
    <ChildView :is-show="isOpen" :row="row"  :row2="row2"> </ChildView>
  </div>
</template>

<script>
import ChildView from './test.vue';
export default {
  components: { ChildView },
  data() {
    return {
      isOpen: false,
      row: {},
      list: [
        { name: '王丽', study: 'Java' },
        { name: '李克', study: 'Python' },
      ],
    };
  },
  methods: {
    // 传递事件
    transmitClick(row) {
      this.isOpen = true;
      this.row2 = {
        name1: 'qwe',
      };
      this.row = {
        name: 3443,
      };
    },
  },
};
</script>
