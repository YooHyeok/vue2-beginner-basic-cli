<template>
  <div>
    <h1>{{ title }}</h1>
    <p>{{ name }}</p>
    <button @click="updateName">Change Name</button>
    <slot name="header" :nameAttr="name"/>
    <slot/> <!-- v-slot:default 영역 -->
    <slot name="footer" :nameAttr="name"/>
  </div>
</template>
<script>
export default {
  name: 'YooHyeokSchool',
  // props: ['title'],
  props: {
    title: {
      type: String,
      required: true,
      default: "default title"
    }
  },
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