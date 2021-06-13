<template>
<!-- 
  https://v3.ko.vuejs.org/guide/template-syntax.html#%E1%84%87%E1%85%A9%E1%84%80%E1%85%A1%E1%86%AB%E1%84%87%E1%85%A5%E1%86%B8-interpolation
  v-once : 데이터를 단 한번만 화면에 랜더링하고 데이터가 변경되더라도 갱신하지 않는다. 일회용
  v-html="" : 이중 중괄호는 데이터를 일반 텍스트로 해석하는데 이를 HTML로 출력하기 위해 사용
  v-bind : 약어로는 :, 속성부분에 실제로 데이터를 채워 넣기 위해 사용
  v-on : 약어로는 @, 이벤트 적용 시 사용
  attr : 속성의 약어, 실제 데이터를 가지고 속성의 이름을 대체해서 사용가능
  event
  -->
  <!-- v-once 사용, v-on사용 약어 @   -->
  <!-- <h1  -->
  <!-- v-once -->
  <!-- @click="add"> -->
    <!-- {{ msg }} -->
  <!-- </h1> -->

  <!-- v-html 사용 -->
  <!-- <h1 v-html="msg"></h1> -->

  <!-- v-bind 사용, 약어 : -->
  <!-- <h1 :class="msg"> -->
  <!-- 약어 미사용 시 -->
  <!-- v-bind:class="msg"> -->

  <!-- class 부분을 []로 대체 --> 
  <!-- ":[attr]"에 "'active'"로 하면 'active'가 문자 데이터로 해석이 된다-->
  <h1 
    :[attr]="'active'"  
    @[event]="add">
    {{ msg }}
  </h1>
</template>

<script>
export default {
  data() {
    return {
      // msg: '<div style="color: blue;">Hello world!</div>'
      msg: 'active',
      attr: 'class',
      event: 'click'
    }
  },
  methods: {
    add() {
      this.msg += '!'
    }
  }
}
</script>

<style scoped>
  .active {
    color: royalblue;
    font-size: 100px;
  }
</style>