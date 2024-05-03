<template>
  <div>{{ message }}</div>
  <button @click="changeMessage">버튼</button>
  <div>
    {{ watchMessage }}
  </div>
</template>

<script>
export default {
  data() {
    return {
      message: '안녕하세요, Vue.js Watch 기능 테스트 문구입니다.',
      watchMessage: '',
    };
  },
  watch: {
    // message: function(){}
    // 데이터 뿐 아니라 computed 로 계산된 형태의 데이터도 watch 로 감지 가능합니다.
    // 보통 게시판에서 한 컬럼을 선택했을 때, 고유한 id 값이 바뀜을 감지하고,
    // 이때, 해당 컬럼의 id 값에 따른 상세 데이터를 호출할 때, 주로 사용합니다.
    message() {
      this.watchMessage = 'Watch 동작';
    },
  },
  methods: {
    changeMessage() {
      console.log('함수 호출');
      this.message = '변경된 message 입니다.';
    },
  },
};
</script>

<style scoped></style>
