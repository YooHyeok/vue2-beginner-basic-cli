<template>
  <div class="about">
    <h1>This is an about page</h1>
    <YooHyeokSchool v-bind="props"/>
    <YooHyeokSchool>
      <template v-slot:header="props"> <!-- 축약형: #header, slot의 props 바인딩 가능 -->
        <div>
          <h1>Header! {{ props.nameAttr }}</h1>
          <p>header!</p>
        </div>
      </template>
      <template v-slot:footer="{ nameAttr }"> <!-- 축약형: #footer -->
        <div>
          <h1>Footer! {{ nameAttr }}</h1>
          <p>footer!</p>
        </div>
      </template>
      <template> <!-- v-slot:default 생략 가능 -->
        <div>
          <h1>Nomal!</h1>
          <p>nomal!</p>
        </div>
      </template>
    </YooHyeokSchool>
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
        title: '어바웃타이틀'
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