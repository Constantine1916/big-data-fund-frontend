<template>
  <div>{{ sean }}</div>
  <button @click="onchange">change</button>
</template>

<script setup lang='ts'>
import { ref } from 'vue';

enum Gender {
  male,
  female
}
interface Man {
  name: string;
  age: number;
  sex: Gender;
}
let sean = ref<Man>({
  name: 'sean',
  age: 23,
  sex: Gender.male
})

const onchange = (): void => {
  sean.value.age = 24;
  console.log('sean', sean);
}
</script>

<style scoped>

</style>