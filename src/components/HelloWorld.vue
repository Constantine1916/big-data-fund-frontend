<!--
 * @Description: 
 * @Author: sunjr
 * @Date: 2022-04-07 17:28:08
 * @FilePath: \vue3_vite_ts_demo\vue3.0_demo1\src\components\HelloWorld.vue
 * @LastEditTime: 2022-07-16 16:17:05
 * @LastEditors: sunjr
-->
<script setup lang="ts">
import { ref, Ref } from 'vue'

defineProps<{ msg: string }>()

const count = ref(0);

console.log("count", count);
console.log("count", count.value);

let message: Ref<string> = ref('true');

const changeMes = () => {
  message.value = 'fake';
  console.log('message', message);
}


type Cls = {
  testA: boolean,
  testB: boolean
}

const cls: Cls = {
  testA: true,
  testB: false
}
</script>

<template>
  <h1>{{ msg }}</h1>
  <br/>
  <div :class="cls"> test cls </div>
  <br/>
  <input v-model="count" type="number">
  {{ count }}
  <br/>
  <button @click="changeMes">changeMes</button>
  {{ message }}
</template>

<style scoped>
.testA {
  color: pink;
}

.testB {
  border: 1px solid red;
}
</style>
