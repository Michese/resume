<template>
  <button class="menu-button" type="button" @click="isOpenMenu = true">
    <svg class="menu-button__image" width="60" height="60" viewBox="0 0 60 60" xmlns="http://www.w3.org/2000/svg">
      <path
        d="M0.35083 0H60V16.3636H0.35083V0ZM0.35083 21.8182H60V38.1818H0.35083V21.8182ZM0.35083 43.6364H60V60H0.35083V43.6364Z"
      />
    </svg>
  </button>
  <teleport to="body">
    <transition name="menu">
      <nav-menu v-if="isOpenMenu" class="menu-button__nav-menu" :items="items" @close="isOpenMenu = false" />
    </transition>
  </teleport>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import { Prop } from 'vue-property-decorator';
import NavMenu from '@/components/navMenu/NavMenu.vue';
import { TLink } from '@/types';

@Options({
  name: 'MenuButton',
  components: { NavMenu },
})
export default class MenuButton extends Vue {
  @Prop({
    required: true,
    type: Array,
  })
  items!: TLink[];
  isOpenMenu = false;
}
</script>

<style lang="scss" scoped>
.menu-button {
  background: transparent;

  &__image {
    fill: black;

    &:hover {
      fill: #fff;
    }
  }
}
</style>
