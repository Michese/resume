<template>
  <header-page />
  <main class="content-page">
    <about />
    <skill />
    <AdvantageSection
      v-for="advantageSection in advantageSections"
      :advantageSection="advantageSection"
      :key="advantageSection.id"
      :id="advantageSection.id"
    />
  </main>
  <footer-page />
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import HeaderPage from '@/components/headerPage/HeaderPage.vue';
import About from '@/components/about/About.vue';
import Skill from '@/components/skill/Skill.vue';
import AdvantageSection from '@/components/advantageSection/AdvantageSection.vue';
import FooterPage from '@/components/footerPage/FooterPage.vue';
import { TAdvantageSection } from '@/types';

@Options({
  components: {
    HeaderPage,
    About,
    Skill,
    AdvantageSection,
    FooterPage,
  },
})
export default class App extends Vue {
  get advantageSections(): TAdvantageSection[] {
    return [
      { caption: 'Образование', id: 'education' },
      { caption: 'Опыт работы', id: 'experience' },
      { caption: 'Достижения', id: 'achievements' },
    ];
  }
}
</script>

<style></style>
