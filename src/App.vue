<script setup lang="ts">
import HelloWorld from './components/HelloWorld.vue'
import { ref, computed } from 'vue';

const name = ref('田中太郎');

// 時計
const now = new Date();
const nowStr = now.toLocaleTimeString();
let timeStr = nowStr;
const timeStrRef = ref(nowStr);

function changeTime(): void {
  const newTime = new Date();
  const newTimeStr = newTime.toLocaleTimeString();
  timeStrRef.value = newTimeStr;
}

setInterval(changeTime, 1000);

// 円の面積
const radiusInit: number = Math.round(Math.random() * 10);
const PI = ref(3.14);
const radius = ref(radiusInit);
</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />
      <!-- 追加 -->
      <p>こんにちは{{ name }}さん！！</p>
    </div>
  </header>

  <main>
    <div>
      <h2>時計</h2>
      <p>現在時刻：{{ timeStr }}</p>
      <p>現在時刻(Ref):{{ timeStrRef }}</p>
    </div>

    <div>
      <h2>computedで円の面積計算</h2>
    </div>
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
