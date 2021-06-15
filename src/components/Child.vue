<template>
  <div>
    Child: {{ msg.value }}
  </div>
</template>


<script>
export default {
  // 계산된 하나의 객체 데이터
  inject: ['msg']
}
</script>