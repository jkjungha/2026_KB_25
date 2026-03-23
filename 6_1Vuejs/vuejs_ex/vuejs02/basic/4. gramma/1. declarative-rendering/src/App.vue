<template>
  <div id="date">
    {{ date
    }}<!-- setup()에서 date에 해당하는 값-->
  </div>
  <div id="date2">
    {{ date2
    }}<!-- data()의 date2에 해당하는 값 -->
  </div>
</template>

<script>
export default {
  // Composition API
  setup() {
    const date = Date().toString();
    return {
      date,
    };
  },

  // Option API
  data() {
    return {
      date2: Date().toString(),
    };
  },
};
</script>
