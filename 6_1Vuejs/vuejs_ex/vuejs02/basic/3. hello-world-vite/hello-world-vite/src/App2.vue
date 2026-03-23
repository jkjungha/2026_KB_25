//오늘 날짜를 시스템으로부터 받아와서 브라우저에 출력
<template>
  <div id="date">
    {{ date }}
  </div>
  <div id="date2"></div>
</template>

<script>
export default {
  data() {
    return {
      date2: Date().toString(),
    };
  },
  setup() {
    const date = Date().toString();
    return {
      date,
    };
  },
};
</script>
