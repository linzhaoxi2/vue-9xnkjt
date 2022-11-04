<template>
  <div class="grand-child-view">
    <p>孙子组件</p>
    <p>
      传给孙子组件的数据：{{ row.name }}
      {{ row.name !== undefined ? '学习' : '' }} {{ row2 }}
    </p>
    <button :aa="isButtonDisabled" @click='downloadVideo("https://vitejs-vite-9e35ri--5173.local-credentialless.webcontainer.io/vite.svg",'name1')'>Button</button>
    {{ number }}
    {{ testFun() }}
  </div>
</template>

<script>
export default {
  // 不想继承所有父组件的内容,同时也不在组件根元素dom上显示属性
  inheritAttrs: false,
  // 在本组件中需要接收从父组件传递过来的数据，注意props里的参数名称不能改变，必须和父组件传递过来的是一样的
  props: {
    isShow: {
      type: Boolean,
      dedault: false,
    },
    row: {
      type: Object,
      dedault: () => {},
    },
    row2: {
      type: Object,
      dedault: () => {},
    },
  },
  data() {
    return {
      number: 1,
      isButtonDisabled: true,
      objectOfAttrs: {
        id: 'container',
        class: 'wrapper',
      },
    };
  },
  methods: {
  downloadVideo(url, name) {
  let link = document.createElement('a')
  link.style.display = 'none'
  link.href = url
  link.setAttribute('download', name)
  document.body.appendChild(link)
  link.click()
  return this.$message.success('下载成功')
},

    testFun() {
      this.number = 10;
    },
  },
};
</script>
