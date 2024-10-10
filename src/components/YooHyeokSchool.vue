<template>
  <div>
    <p>{{ name }}</p>
    <button @click="updateName">Change Name</button>
  </div>
</template>
<script>
export default {
  name: 'YooHyeokSchool',
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

</style>