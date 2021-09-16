<template>
  <header-page />
  <main class="content-page">
    <about />
    <skill />
  </main>
  <footer-page />
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import HeaderPage from '@/components/headerPage/HeaderPage.vue';
import FooterPage from '@/components/footerPage/FooterPage.vue';
import About from '@/components/about/About.vue';
import Skill from '@/components/skill/Skill.vue';

@Options({
  components: {
    HeaderPage,
    About,
    Skill,
    FooterPage,
  },
})
export default class App extends Vue {}
</script>

<style></style>
