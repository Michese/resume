<template>
  <section class="skill">
    <h2 class="skill__section-caption section-caption">Навыки</h2>

    <div class="skill__inner">
      <div class="skill__card">
        <ul v-for="(skillItems, index) in skillLists" class="skill__list" :key="'skill' + index">
          <li v-for="skill in skillItems" class="skill__item" :key="skill.name">
            <header class="skill__header">
              <h3 class="skill__name">{{ skill.name }}</h3>
              <span class="skill__percent">{{ skill.percent }}%</span>
            </header>
            <main class="skill__main">
              <div class="skill__progress" :style="{ width: `${skill.percent}%` }"></div>
            </main>
          </li>
        </ul>
      </div>
    </div>
  </section>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';

@Options({
  name: 'Skill',
})
export default class Skill extends Vue {
  get skillLists(): { name: string; percent: number }[][] {
    return [
      [
        { name: 'HTML', percent: 65 },
        { name: 'CSS', percent: 50 },
        { name: 'SCSS', percent: 70 },
      ],
      [
        { name: 'JavaScript', percent: 90 },
        { name: 'TypeScript', percent: 80 },
        { name: 'Vue.js', percent: 80 },
      ],
    ];
  }
}
</script>

<style lang="scss" scoped>
.skill {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
  max-width: var(--container-width);
  padding: 30px 15px 15px;
  margin: 0 auto;

  &__section-caption {
    text-align: center;
    margin-bottom: 26px;
  }

  &__inner {
    display: flex;
    flex: 1 0 100%;
    justify-content: center;
    flex-direction: column;
    height: 100%;
  }

  &__card {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    width: 100%;

    padding: 57px 30px;
    background: #fff;
    box-shadow: 0 0 15px 2px rgba(0, 0, 0, 0.48);
    border-radius: 30px;
  }

  &__list {
    width: 100%;
    &:not(:last-child) {
      margin-bottom: 24px;
    }
  }

  &__item:not(:last-child) {
    margin-bottom: 24px;
  }

  &__header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 15px;
  }

  &__name,
  &__percent {
    font-size: 23px;
    line-height: 1.21739em;
    color: var(--orange-color);
  }

  &__main {
    position: relative;
    height: 10px;
    background-color: var(--gray-color);
  }

  &__progress {
    position: absolute;
    top: 0;
    bottom: 0;
    left: 0;
    background-color: var(--orange-color);
  }
}

@media screen and (min-width: 500px) {
  .skill {
    padding: 98px 75px 30px 75px;
  }
}

@media screen and (min-width: 1110px) {
  .skill {
    &__card {
      flex-direction: row;
    }

    &__list:not(:last-child) {
      margin-right: 30px;
    }
  }
}
</style>
