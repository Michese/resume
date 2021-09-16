<template>
  <header class="header-page">
    <div class="header-page__inner">
      <a href="tel:+79046867942" class="header-page__phone-link">
        <img src="./assets/phone.svg" alt="phone" class="header-page__phone-image" />
      </a>
      <socials class="header-page__socials" />
      <menu-button :items="itemsMenu" />
    </div>
  </header>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import Socials from '@/components/socials/Socials.vue';
import MenuButton from '@/components/menuButton/MenuButton.vue';
import { TLink } from '@/types';

@Options({
  name: 'HeaderPage',
  components: { Socials, MenuButton },
})
export default class HeaderPage extends Vue {
  get itemsMenu(): TLink[] {
    return [
      {
        text: 'О себе',
        link: '#',
      },
      {
        text: 'Навыки',
        link: '#',
      },
      {
        text: 'Образование',
        link: '#',
      },
      {
        text: 'Опыт',
        link: '#',
      },
      {
        text: 'Достижения',
        link: '#',
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
    padding: 28px 15px;
  }

  &__socials {
    display: none;
  }
}

@media screen and (min-width: 1110px) {
  .header-page {
    &__socials {
      display: block;
    }
  }
}
</style>
