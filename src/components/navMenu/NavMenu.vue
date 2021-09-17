<template>
  <nav class="nav-menu">
    <button class="nav-menu__button" type="button" @click.stop="close">
      <svg width="60" height="60" viewBox="0 0 60 60" xmlns="http://www.w3.org/2000/svg" class="nav-menu__image">
        <path d="M60 6L54 0L30 24L6 0L0 6L24 30L0 54L6 60L30 36L54 60L60 54L36 30L60 6Z" />
      </svg>
    </button>
    <ul class="nav-menu__list">
      <li v-for="item in items" :key="item.text" class="nav-menu__item" @click.stop="close">
        <a :href="item.link" class="nav-menu__link">{{ item.text }}</a>
      </li>
    </ul>
  </nav>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import { Prop, Emit } from 'vue-property-decorator';
import { TLink } from '@/types';

@Options({
  name: 'NavMenu',
})
export default class NavMenu extends Vue {
  @Prop({
    default: [],
  })
  items: TLink[] = [];
  @Emit('close') close(): boolean {
    return false;
  }
}
</script>

<style lang="scss" scoped>
.nav-menu {
  display: flex;
  flex-direction: column;

  position: fixed;
  right: 0;
  top: 0;
  z-index: 5;
  padding: 28px 15px 60px 64px;
  background-color: var(--black-color);
  border-radius: 0 0 0 30px;

  &__button {
    align-self: flex-end;
    margin-bottom: 60px;
    background-color: transparent;

    &:hover {
      color: #fff;
    }
  }

  &__image {
    fill: var(--orange-color);

    &:hover {
      fill: #fff;
    }
  }

  &__list {
    margin-right: 55px;
  }

  &__item:not(:last-child) {
    margin-bottom: 33px;
  }

  &__link {
    font-size: 26px;
    line-height: 1.230769em;
    color: var(--orange-color);

    &:hover {
      color: #fff;
    }
  }
}

@media screen and (min-width: 1110px) {
  .nav-menu {
    display: none;
  }
}
</style>
