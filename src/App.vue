<template>
  <div id="app">
    <div class="container">
      <div
        class="item"
        v-for="(item, index) in list"
        :style="{
          height: item.height * 10 + 'px',
          backgroundColor: item.color
        }"
        :key="index"
      >
        {{ item.height }}
      </div>
    </div>
    <button @click="changeSort">点击切换排序{{ flag }}</button>
  </div>
</template>

<script>
export default {
  name: 'App',
  data () {
    return {
      list: [
        { height: 10, color: 'red' },
        { height: 8, color: 'green' },
        { height: 15, color: 'blue' },
        { height: 6, color: 'yellow' },
        { height: 2, color: 'black' }
      ],
      flag: true
    }
  },
  methods: {
    changeSort () {
      this.flag
        ? this.list.sort((a, b) => a.height - b.height)
        : this.list.reverse()
      this.flag = !this.flag
    }
  }
}
</script>

<style>
.container {
  display: flex;
  align-items: flex-end;
  border: 1px solid #000;
}
.container .item {
  width: 50px;
}
</style>
