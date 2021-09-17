<template>
  <header class="header-page">
    <div class="header-page__inner">
      <a href="tel:+79046867942" class="header-page__phone-link">
        <img src="./assets/phone.svg" alt="phone" class="header-page__phone-image" />
      </a>
      <socials class="header-page__socials" />
      <div class="header-page__menu-button">
        <menu-button class="header-page__menu-button" :items="itemsMenu" />
      </div>
      <nav class="header-page__navigation">
        <ul class="header-page__list">
          <li v-for="item in itemsMenu" class="header-page__item" :key="item.text">
            <a :href="item.link" class="header-page__link">{{ item.text }}</a>
          </li>
        </ul>
      </nav>
    </div>
  </header>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import Socials from '@/components/socials/Socials.vue';
import MenuButton from '@/components/menuButton/MenuButton.vue';
import { TLink } from '@/types';
import { menuLinksEnum } from '@/enums';

@Options({
  name: 'HeaderPage',
  components: { Socials, MenuButton },
})
export default class HeaderPage extends Vue {
  get itemsMenu(): TLink[] {
    return [
      {
        text: 'О себе',
        link: '#' + menuLinksEnum.about,
      },
      {
        text: 'Навыки',
        link: '#' + menuLinksEnum.skills,
      },
      {
        text: 'Образование',
        link: '#' + menuLinksEnum.education,
      },
      {
        text: 'Опыт работы',
        link: '#' + menuLinksEnum.experience,
      },
      {
        text: 'Достижения',
        link: '#' + menuLinksEnum.achievements,
      },
    ];
  }
}
</script>

<style lang="scss" scoped>
.header-page {
  width: 100%;
  position: fixed;
  z-index: 1;
  background-color: rgba(249, 138, 35, 0.8);

  &__inner {
    display: flex;
    justify-content: space-between;
    align-items: center;
    max-width: var(--container-width);
    padding: 28px 15px;
    margin: 0 auto;
  }

  &__list {
    display: flex;
  }

  &__item:not(:last-child) {
    margin-right: 33px;
  }

  &__link {
    font-size: 20px;
    line-height: 24px;
    &:hover {
      color: #fff;
    }
  }

  &__socials {
    display: none;
  }

  &__navigation {
    display: none;
  }
}

@media screen and (min-width: 1110px) {
  .header-page {
    &__socials {
      display: block;
    }

    &__phone-link {
      display: none;
    }

    &__menu-button {
      display: none;
    }

    &__navigation {
      display: block;
    }
  }
}
</style>
