<template>
  <div class="about">
    <h1>This is an about page</h1>
    <YooHyeokSchool/>

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