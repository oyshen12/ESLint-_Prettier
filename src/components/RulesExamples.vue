<script setup lang="ts">
interface IProps {
  msg?: string;
}

withDefaults(defineProps<IProps>(), {
  msg: 'qwe',
});

//"no-await-in-loop": "error"
async function foo() {
  for (let i = 0; i < 10; i++) {
    // Bad: each loop iteration is delayed until the entire asynchronous operation completes
    await new Promise((res) => {
      setTimeout(res, 1000);
    });
  }
}
foo();

// "no-promise-executor-return": "error"
new Promise(() => {
  return '11';
});

//  "no-self-compare": "error"
const x = 10;
if (x === x) {
  //
}

// "no-template-curly-in-string": "error"
console.log('Hello ${name}!');

// "no-unmodified-loop-condition": "error"
const node = 1;
while (node) {
  console.log('node ', node);
}

// "no-unreachable-loop": "error"
for (let i = 0; i < 10; i++) {
  if (i === 3) {
    console.log('i ', i);
  }
  break;
}

// "require-atomic-updates": "error"
let totalLength = 0;
const addLengthOfSinglePage = async (pageNum: number): Promise<void> => {
  totalLength += await new Promise<number>((res) => {
    setTimeout(() => {
      res(pageNum);
    });
  });
};

Promise.all([addLengthOfSinglePage(1), addLengthOfSinglePage(2)]).then(() => {
  console.log('The combined length of both pages is', totalLength);
});
</script>

<template>
  <h1>{{ msg }}</h1>

  <div class="card">
    <button type="button" class="button-classssssssssssssssssssssssssssssssssssssssssss" id="button-id"></button>
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
