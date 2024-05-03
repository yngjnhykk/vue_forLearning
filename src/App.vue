<template>
  <div>
    <h1>
      {{ text }}
    </h1>
    <h2>changeText 함수 호출 값: {{ changeText() }}</h2>
    <h2>changeText 함수 호출 값: {{ changeText() }}</h2>
    <h2>changeText 함수 호출 값: {{ changeText() }}</h2>

    <h3>{{ computedText }}</h3>
    <h3>{{ computedText }}</h3>
    <h3>{{ computedText }}</h3>
  </div>
</template>

<script>
export default {
  data() {
    return {
      text: 'Computed Text data',
    };
  },
  // methods 부분에 선언된 함수와 동일한 로직일 때,
  // 캐싱 기능이 있는 methods 는 호출될 때마다 console 값이 출력이 되었습니다.
  // 반면에 computed 는 캐싱 기능이 있기 때문에
  // methods 와 어떤 차이점이 있는지 확인하는 것이 포인트입니다.
  computed: {
    computedText() {
      console.log('Computed 기능 생성');

      return this.text.split('').reverse().join('');
    },
  },
  methods: {
    changeText() {
      console.log('함수 호출');
      console.log(this.text);

      return this.text.split('').reverse().join('');
    },
  },
};
</script>

<style scoped></style>
