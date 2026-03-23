<!-- 데이터 결합을 통한 사용자 입력 처리 예제
 v-model, v-bind 컴포넌트에서 선언한 변수와 HTML태그의 속성을 결합
  v-bind디렉티브는 템플릿을 통해서 변수값을 변경시킬 수 없음
 v-model은 템플릿을 통해 변수의 값을 변경시킬 수 있음
-->
<template>
  <p>줄임말과 원래말을 입력하세요.</p>
  <input
    type="text"
    v-bind:value="abbr"
  /><!--단방향 바인딩, abbr에 따라 출력되는 값이 다름, 단 사용자가 입력한 값이 abbr변수에 반영되지 않음-->
  <input
    type="text"
    v-model="normal"
  /><!--양방향 바인딩, normal에 따라 출력되는 값이 다름, 사용자가 입력한 값이 normal 변수에 반영됨-->
  <hr />
  <abbr v-bind:title="normal">{{ abbr }}</abbr>
</template>

<script>
import { ref } from 'vue';

export default {
  // Composition API
  setup() {
    const abbr = ref('KB');
    const normal = ref('KB Project');
    return {
      abbr,
      normal,
    };
  },
};
</script>
