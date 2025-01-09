<script setup lang="ts">
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

// "id-match": ["error", "^[a-z]+([A-Z][a-z]+)*$"]
const my_favorite_color = '#112C85';
console.log('i ', my_favorite_color);

// "init-declarations": ["error", "always"]
let b;
console.log(b);

// "@typescript-eslint/explicit-function-return-type": "error",
function test() {
  return;
}
test();
</script>

<template>
  <h1>ESLint-Prettier-Stylelint Config</h1>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
