<template>
  <h2>Small Items</h2>
  <p v-for="item in small_items_c" :key="item.id">{{ item.text }}</p>
  <!--옵션 아이템 중 id가 3보다 작은 객체만 골라 객체의 text 값을 하나씩 출력-->
  <p v-for="item in small_items_o" :key="item.id">{{ item.text }}</p>
  <!--옵션 아이템 중 id가 3보다 작은 객체만 골라 객체의 text 값을 하나씩 출력-->
  <h2>Big Items</h2>
  <p v-for="item in big_items_c" :key="item.id">{{ item.text }}</p>
  <!--아이템 중 id가 3와 같거나 큰 객체만 골라 객체의 text 값을 하나씩 출력-->
  <p v-for="item in big_items_o" :key="item.id">{{ item.text }}</p>
  <!--옵션 아이템 중 id가 3와 같거나 큰 객체만 골라 객체의 text 값을 하나씩 출력-->
</template>
<!-- :key="item.id"을 사용하여 마커가 출력되지 않음 -->
<script>
import { reactive, computed } from 'vue';

export default {
  //Options API
  data() {
    return {
      arr: [
        { id: 1, text: '1번 옵션 아이템' },
        { id: 2, text: '2번 옵션 아이템' },
        { id: 3, text: '3번 옵션 아이템' },
        { id: 4, text: '4번 옵션 아이템' },
        { id: 5, text: '5번 옵션 아이템' },
      ],
    };
  },
  computed: {
    small_items_o() {
      return this.arr.filter((i) => i.id < 3);
    },
    big_items_o() {
      return this.arr.filter((i) => i.id >= 3);
    },
  },
  // Composition API
  setup() {
    const arr = reactive([
      { id: 1, text: '1번 아이템' },
      { id: 2, text: '2번 아이템' },
      { id: 3, text: '3번 아이템' },
      { id: 4, text: '4번 아이템' },
      { id: 5, text: '5번 아이템' },
    ]);

    const small_items_c = computed(() => {
      return arr.filter((i) => i.id < 3);
    });
    const big_items_c = computed(() => {
      return arr.filter((i) => i.id >= 3);
    });

    return {
      small_items_c,
      big_items_c,
    };
  },
};
</script>
