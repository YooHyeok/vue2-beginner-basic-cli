<template>
  <div>
    <form action="">
      <InputField :name="name" @changeName="changeName"/>
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
    changeName(name) {
      this.name = name
    },
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