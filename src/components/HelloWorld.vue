<script setup lang="ts">
import { ref } from 'vue';

interface IProps {
  msg?: string;
}

withDefaults(defineProps<IProps>(), {
  msg: 'qwe',
});

const count = ref(0);
const tmp = 'qwe';
console.log('tmp ', tmp);
const check = (qwe: string) => qwe;
check('qwe');
</script>

<template>
  <h1>{{ msg }}</h1>

  <div class="card">
    <button
      type="button"
      class="button-classssssssssssssssssssssssssssssssssssssssssss"
      id="button-id"
      @click="count++"
    >
      count is {{ count }}
    </button>
    <p>
      Edit
      <code>components/HelloWorld.vue</code> to test HMR
    </p>
  </div>

  <p>
    Check out
    <a href="https://vuejs.org/guide/quick-start.html#local" target="_blank">create-vue</a>, the official Vue + Vite
    starter
  </p>
  <p>
    Install
    <a href="https://github.com/vuejs/language-tools" target="_blank">Volar</a>
    in your IDE for a better DX
  </p>
  <p class="read-the-docs">Click on the Vite and Vue logos to learn more</p>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
