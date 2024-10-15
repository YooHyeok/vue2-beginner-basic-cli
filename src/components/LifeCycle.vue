<template>
  <div>
    <br>
    {{ name }}
    <button @click="updateName">updateName</button>
  </div>
</template>
<script>
export default {
  data() {
    return {
      name:'LifeCycle'
    }
  },
  beforeCreate() {console.log("beforeCreate", this.name)},
  created() {console.log("created", this.name)},
  beforeMount() {console.log("beforeMount", this.name)},
  mounted() {
    console.log("mounted", this.name)
    this.updateName();
  },
  beforeUpdate() {console.log("beforeUpdate", this.name)},
  updated() {console.log("updated", this.name)},
  beforeDestroy() {console.log("beforeDestroy", this.name)}, // about 컴포넌트로 route할 경우 실행됨
  destroyed() {console.log("destroyed", this.name)},
  methods: {
    updateName() {
      this.name='LifeCycle: '
    }
  }
}
</script>