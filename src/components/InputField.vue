<template>
  <div>
    <label for="">Name</label>
    <!-- <input 
      type="text" 
      :value="name" 
      style="padding: 30px; border: 2px solid green"
      @input=" changeName"
    > -->
    <input 
      type="text" 
      :value="name" 
      style="padding: 30px; border: 2px solid green"
      @input="$emit('changeName', $event.target.value)"
    >
  </div>
</template>

<script>
export default {
  props: {
    name: {
      type: String,
      required: true,
      default: null
    },
  },
  /* methods: {
    changeName(e) {
      this.$emit('changeName', e.target.value)
    }
  } */
}
</script>
