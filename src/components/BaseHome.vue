<template>
  <div class="baseHome">
    <base-header />
    <main class="baseHome__main">
      <ul>
        <li v-for="poem in poems" :key="poem.id">
          <h2>{{ poem.title }}</h2>
          <div v-html="poem.text"></div>
        </li>
      </ul>
    </main>
    <base-footer />
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import data from '../../data.json';
import BaseFooter from './BaseFooter.vue';
import BaseHeader from './BaseHeader.vue';

const poems = ref(data);
</script>

<style scoped lang="scss">
.baseHome {
  display: flex;
  flex-direction: column;
  height: 100vh;
  padding: 20px;

  &__main {
    flex-grow: 2;
    display: flex;
    flex-direction: column;
    justify-content: center;
  }
}
</style>  