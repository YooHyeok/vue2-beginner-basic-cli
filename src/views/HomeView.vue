<template>
  <div>
    <h1>This is a Home page</h1>
    <p>{{ name }}</p>
    <button @click="updateName">Change Name</button>
    <yoo-hyeok-school/>
  </div>
</template>
<script>
import YooHyeokSchool from '@/components/YooHyeokSchool.vue'
export default {
  components: { YooHyeokSchool },
  data() {
    return {
      name: 'YooHyeok School'
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