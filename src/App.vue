<template>
  <header-page />
  <main class="content-page"></main>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import HeaderPage from '@/components/headerPage/HeaderPage.vue';
import FooterPage from '@/components/footerPage/FooterPage.vue';

@Options({
  components: {
    HeaderPage,
    FooterPage,
  },
})
export default class App extends Vue {}
</script>

<style></style>
