<template>
  <div>
    <form action="">
      <!-- <InputField :name="name" @changeName="changeName"/>  --> <!-- $emit으로 넘긴 값을 간접적으로 받을 경우 값에 해당하는 $event를 해당 함수의 인자로 자동 전달 -->
      <!-- <InputField :name="name" @changeName="name=$event"/> --> <!-- $emit으로 넘긴 값을 직접적으로 받을 경우 $event로 바로 받는다. -->
      <InputField v-model="name"/> <!-- v-model은 내부적으로 @input="name"과 :value="name"이 적용되므로 emit에서 input을 호출한다. (props가 value로 넘어감) -->
      <button>Submit</button>
    </form>
    <h1>This is a Home page</h1>
    <p>{{ name }}</p>
    <button @click="updateName">Change Name</button>
    <YooHyeokSchool />
    <yoo-hyeok-school v-bind="props"/>
    <yoo-hyeok-school :title="5"/>
  </div>
</template>
<script>
import YooHyeokSchool from '@/components/YooHyeokSchool.vue'
import InputField from '@/components/InputField.vue'
export default {
  components: { YooHyeokSchool, InputField },
  data() {
    return {
      name: 'YooHyeok School',
      props: {
        title: '홈타이틀'
      }
    }
  },
  methods: {
    /* changeName(name) {
      this.name = name
    }, */
    updateName() {
      this.name = 'YooHyeok School Updated'
    }
  }
}
</script>
<style scoped>
  h1 {
    color: red;
  }
</style>