<template>
  <nav class="nav-menu">
    <button class="nav-menu__button" type="button" @click.stop="close">
      <img src="./assets/close.svg" alt="close" class="nav-menu__image" />
    </button>
    <ul class="nav-menu__list">
      <li v-for="item in items" :key="item.text" class="nav-menu__item">
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

  &__button {
    align-self: flex-end;
    margin-bottom: 60px;
    background-color: transparent;
  }

  &__list {
    margin-right: 55px ;
  }
}
</style>
