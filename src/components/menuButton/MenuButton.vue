<template>
  <button class="menu-button" type="button" @click="isOpenMenu = true">
    <img src="./assets/bars.svg" alt="bars" class="menu-button__image" />
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
}
</style>
