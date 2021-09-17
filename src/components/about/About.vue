<template>
  <section class="about">
    <div class="about__inner">
      <div class="about__card">
        <strong class="about__name">Куликов Вадим Юрьевич</strong>
        <strong class="about__profession">Vue-разработчик</strong>
        <img src="./assets/photo.jpg" alt="photo" class="about__avatar" />
      </div>

      <div class="about__content">
        <h2 class="about__caption section-caption">О себе</h2>
        <p class="about__description">
          Главными преимуществами считаю умение мыслить аналитически и способность быстро принимать решение. Помимо этих
          качеств, можно отметить стрессоустойчивость, ответственность, умение работать в команде.
        </p>
        <div class="about__white-line"></div>
        <ul class="about__list">
          <li v-for="item in definitions" class="about__item" :key="item.term">
            <strong class="about__term">{{ item.term }}</strong>
            <a v-if="item.link" class="about__definition about__definition_link" :href="item.link">{{
              item.definition
            }}</a>
            <span v-else class="about__definition">{{ item.definition }}</span>
          </li>
        </ul>
      </div>
    </div>
  </section>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';

@Options({
  name: 'About',
})
export default class About extends Vue {
  get definitions(): { term: string; definition: string; link?: string }[] {
    return [
      { term: 'Город', definition: 'Липецк' },
      { term: 'Дата рождения', definition: '16.05.1998' },
      { term: 'Электронный адрес', definition: 'Michese48@mail.ru', link: 'mailto: Michese48@mail.ru' },
      { term: 'Телефон', definition: '+79046867942', link: 'tel: +79046867942' },
    ];
  }
}
</script>

<style lang="scss" scoped>
.about {
  background-color: var(--orange-color);

  &__inner {
    display: flex;
    flex-direction: column;
    align-items: center;
    max-width: var(--container-width);
    margin: 0 auto;
    padding: 174px 15px 60px;
  }

  &__card {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 24px 60px 35.28px;
    margin-bottom: 36px;
    background: rgba(255, 255, 255, 0.25);
    box-shadow: 0 0 30px 5px rgba(0, 0, 0, 0.25);
    border-radius: 5px;
  }

  &__name {
    font-size: 28px;
    line-height: 1.2142857em;
    font-weight: 800;
    margin-bottom: 17px;
  }

  &__profession {
    font-size: 23px;
    line-height: 1.2142857em;
    font-weight: 700;
    margin-bottom: 28px;
  }

  &__avatar {
    border-radius: 50%;
  }

  &__content {
    width: 100%;
    padding: 24px 15px 0;
    margin-bottom: 139px;
  }

  &__caption {
    margin-bottom: 20px;
  }

  &__description {
    font-size: 20px;
    line-height: 1.6em;
    margin-bottom: 35px;
  }

  &__white-line {
    height: 4px;
    width: 80%;
    margin-bottom: 35px;
    background-color: #fff;
    border-radius: 1px 10px 10px 1px;
  }

  &__list {
    width: 100%;
  }

  &__item {
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-gap: 20px;
    &:not(:last-child) {
      margin-bottom: 30px;
    }
  }

  &__term {
    font-weight: 700;
    font-size: 18px;
    line-height: 22px;
    margin-right: 20px;
  }

  &__definition {
    font-weight: 500;
    font-size: 18px;
    line-height: 22px;

    &_link:hover {
      color: red;
    }
  }
}
</style>
