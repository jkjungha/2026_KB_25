<template>
  <div style="width: 200px">
    <ol>
      <li v-for="item in items">{{ item }}</li>
      <!-- items 객체 내 값들을 하나씩 출력함 -->
      <!-- :key=""을 사용하지 않아 마커가 출력됨 -->
    </ol>
  </div>
</template>

<script>
import { reactive } from 'vue';

export default {
  // Composition API
  setup() {
    const items = reactive({ 1: '1번 객체', 2: '2번 객체', 3: '3번 객체' });
    // 여러 객체나 배열 전체를 반응형으로 만들 때 reactive()함수를 사용함
    return {
      items,
    };
  },
};
</script>
