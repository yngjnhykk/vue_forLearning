<template>
  <div>{{ rawHtml }}</div>
  <div>{{ rawHtml2 }}</div>
  <h3 v-html="rawHtml2"></h3>

  <h3 v-bind:class="{ active: isActive }">바아보</h3>
  <h3 :class="{ active: isActive }">바아보</h3>
  <button @click="change">버튼</button>

  <h3 style="color: red; font-size: 24px">스타일 바인딩 테스트</h3>
  <h3 :style="{ color: fontColor, fontSize: fontSize + 'px' }">스타일 바인딩 테스트</h3>
</template>

<script>
export default {
  data() {
    return {
      rawHtml: '이것은 텍스트입니다.',
      rawHtml2: '<span style="color: red">이것은 빨간색이어야 합니다.</span>',
      isActive: false,
      fontColor: '#888888',
      fontSize: 48,
    };
  },
  methods: {
    change() {
      this.isActive = !this.isActive;
    },
  },
};
</script>

<style scoped>
h3.active {
  color: green;
}
</style>
