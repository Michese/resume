<template>
  <header-page />
  <main class="content-page">
    <about :id="getMenuLinks.about" />
    <skill :id="getMenuLinks.skills" />
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
import { menuLinksEnum } from '@/enums';
import olympiadImage from '@/assets/olympiad.jpg';
import championshipImage from '@/assets/championship.jpg';

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
      {
        caption: 'Образование',
        id: menuLinksEnum.education,
        list: [
          {
            link: 'https://stu.lipetsk.ru/',
            isDownload: false,
            caption: 'ЛГТУ',
            year: '2019 - 2023',
            definition: 'Липецкий Государственный Технический Университет',
            content:
              'Высшее учебное заведение в Липецке. Основан в 1956 году как вечерний факультет Тульского механического института приказом Министерства высшего образования СССР от 1 ноября 1956 года № 869.',
          },
          {
            link: 'https://gb.ru/go/LV4~fq',
            isDownload: false,
            caption: 'Geekbrains',
            year: '2021',
            definition: 'Продвинутый курс Javascript',
            content:
              'Российская компания в сфере онлайн-образования. Основана в 2010 году. С 2016 года входит в состав Mail.ru Group. Входит в пятёрку ведущих российских компаний онлайн-образования.',
          },
        ],
      },
      {
        caption: 'Опыт работы',
        id: menuLinksEnum.experience,
        list: [
          {
            link: 'https://greenatom.ru/about_company/',
            isDownload: false,
            caption: 'Greenatom',
            year: '2021',
            definition: 'Стажер отдела web-разработки',
            content:
              'ИТ-интегратор Госкорпорации «Росатом». Компания ведет собственную разработку ПО, осуществляет поддержку и развитие корпоративных ИТ-систем, разрабатывает программных роботов, занимается проектным управлением, импортозамещением, применяет искусственный интеллект и машинное обучение.',
          },
        ],
      },
      {
        caption: 'Достижения',
        id: menuLinksEnum.achievements,
        list: [
          {
            link: olympiadImage,
            isDownload: true,
            caption: '“Умный город”',
            year: '2021',
            definition: 'Победитель олимпиады НТИ по профилю “Умный город”',
            content:
              'Некоммерческая организация созданная Постановлением председателя Правительства РФ Дмитрия Медведева для объединения представителей бизнеса и экспертных сообществ для развития в России перспективных технологических рынков и отраслей, которые могут стать основой мировой экономики.',
          },
          {
            link: championshipImage,
            isDownload: true,
            caption: '“РазРеши”',
            year: '2021',
            definition: 'Призер III чемпионата по решению кейсов НЛМК “РазРеши”',
            content: 'Корпоративный чемпионат группы НЛМК по решению кейсов среди студенческих команд.',
          },
        ],
      },
    ];
  }

  get getMenuLinks(): { [key: string]: string } {
    return menuLinksEnum;
  }
}
</script>

<style></style>
