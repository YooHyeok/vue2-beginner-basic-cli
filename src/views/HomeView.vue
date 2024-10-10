<template>
  <div>
    <h1>This is a Home page</h1>
    <p>{{ name }}</p>
    <button @click="updateName">Change Name</button>
  </div>
</template>
<script>
export default {
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