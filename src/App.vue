<template>
  <div id="app">
    <div class="container">
      <div
        class="item"
        :style="{ height: item * 10 + 'px', backgroundColor: colorList[index] }"
        v-for="(item, index) in list"
        :key="index"
      >
        {{ item }}
      </div>
    </div>
    <button @click="changeSort">点击切换排序</button>
  </div>
</template>

<script>
export default {
  name: 'App',
  data () {
    return {
      list: [10, 8, 15, 6, 2],
      colorList: ['red', 'green', 'blue', 'yellow', 'black'],
      flag: false
    }
  },
  methods: {
    changeSort () {
      function sortDec (a, b) {
        return a - b
      }
      function sortAdd (a, b) {
        return b - a
      }
      if (this.flag) {
        this.list.sort(sortDec)
        window.console.log(this.list)
      } else {
        this.list.sort(sortAdd)
        window.console.log(this.list)
      }
    }
  }
}
</script>

<style>
.container {
  display: flex;
  align-items: start;
  width: 500px;
  height: 500px;
  border: 1px solid #000;
}
.container .item {
  width: 50px;
}
</style>
