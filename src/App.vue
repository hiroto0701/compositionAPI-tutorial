<script setup lang="ts">
import HelloWorld from './components/HelloWorld.vue'
import { ref } from 'vue';

const url = ref("https://github.com/hiroto0701");
const disabled = ref(true);

const imgAttributes = ref({
  src: "./src/assets/logo.svg",
  alt: "vueのロゴ",
  width: 75,
  height: 75
});
</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />
    </div>
  </header>

  <main>
    <p><a :href="url">Github account</a></p>
    <p><button type="button" :disabled="disabled">機能しないボタンです</button></p>

    <p><img v-bind="imgAttributes"></p>
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
