<template>
  <header-page />
  <main class="content-page">
    <about></about>
  </main>
  <footer-page />
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import HeaderPage from '@/components/headerPage/HeaderPage.vue';
import FooterPage from '@/components/footerPage/FooterPage.vue';
import About from '@/components/about/About.vue';

@Options({
  components: {
    HeaderPage,
    About,
    FooterPage,
  },
})
export default class App extends Vue {}
</script>

<style></style>
