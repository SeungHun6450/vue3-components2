<!-- Components Slot --> 
<!-- Fallback Contents : App.vue에서 MyBtn content에 내용이 없을 때 <slot>안의 content가 대체되서 나온다 -->
<!-- Named Slot : 이름을 갖는 슬롯, 내용의 순서를 지켜서 동작하게 하기 위해 사용 -->
<template>
  <div class="btn">
    <slot name="icon"></slot>
    <slot name="text"></slot>
  </div>
</template>


<style scoped>
  .btn {
    display: inline-block;
    margin: 4px;
    padding: 6px 12px;
    border-radius: 4px;
    background-color: gray;
    color: white;
    cursor: pointer;
  }
</style>