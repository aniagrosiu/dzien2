<script setup>
import { ref } from 'vue';
import { dzien2_backend } from 'declarations/dzien2_backend/index';
import Blog from './components/Blog.vue'
let greeting = ref('');

async function handleSubmit(e) {
  e.preventDefault();
  const target = e.target;
  const name = target.querySelector('#name').value;
  const numer = target.querySelector('#numer').value;
  await dzien2_backend.greet(name, Number(numer)).then((response) => {
    greeting.value = response;
  });
}
</script>

<template>
  <main>
    <img src="/logo2.svg" alt="DFINITY logo" />
    <br />
    <br />
    
    <Blog />
  </main>
</template>
