<template>
  <div>
    <h1>This is a Home page</h1>
    <p>{{ name }}</p>
    <button @click="updateName">Change Name</button>
    <YooHyeokSchool />
    <yoo-hyeok-school v-bind="props"/>
  </div>
</template>
<script>
import YooHyeokSchool from '@/components/YooHyeokSchool.vue'
export default {
  components: { YooHyeokSchool },
  data() {
    return {
      name: 'YooHyeok School',
      props: {
        title: '홈타이틀'
      }
    }
  },
  methods: {
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