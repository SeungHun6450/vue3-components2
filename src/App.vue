<!-- Components Slot --> 
<!-- v-slot : 약어 #, 순서를 바꿔도 MyBtn에서 설정한 slot 순서대로 출력된다 --> 
<!--
 <template>
  <MyBtn>
    <template #text>
      <span>Banana</span> 
    </template>
    <template #icon>
      <span>(B)</span>
    </template>
  </MyBtn>
</template>

<script>
import MyBtn from '~/components/MyBtn'

export default {
  components: {
    MyBtn
  }
}
</script>
-->

<!-- Provide / Inject -->
<!--
<template>
  <button @click="message = 'Good?'">
    Click!
  </button>
  <h1>App: {{ message }}</h1>
  <Parent />
</template>

<script>
import Parent from '~/components/Parent'
// provide는 반응성이 제공되지 않아 computed를 사용하여 반응성을 가지게 만든다
import { computed } from 'vue'

export default {
  components: {
    Parent
  },
  data() {
    return {
      message: 'Hello world!'
    }
  },
  provide() {
    // Parent, child의 props를 사용하지 않아도 된다.
    // provide를 사용하면 Parent를 거치지 않고 바로 Child요소로 가게 된다
    // 마지막 child에 inject를 사용한다
    return {
      msg: computed(() => this.message)
      // msg: computed(() => {
      //   return this.message
      // })
    }
  }
}
</script>
-->


<!-- Refs : reference 참조 -->
<template>
  <Hello ref="hello"/>
</template>

<script>
import Hello from '~/components/Hello'

export default {
  components: {
    Hello
  },
  mounted() {
    // const h1El = document.querySelector('h1')
    // console.log(h1El.textContent)

    // refs 사용
    // console.log(this.$refs.hello)

    // 최상위 요소가 하나 이상이면 $el을 사용하면 정확하게 어떤 요소를 바라보는지 알 수 없어서 어떠한 객체 데이터가 출력됨
    console.log(this.$refs.hello.$el)
    // 원하는 good 요소만 참조
    console.log(this.$refs.hello.$refs.good)
  }
}
</script>