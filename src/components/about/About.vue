<template>
  <section class="about">
    <div class="about__inner">
      <div class="about__card">
        <h2 class="about__name">Куликов Вадим Юрьевич</h2>
        <strong class="about__profession">Vue-разработчик</strong>
        <img src="./assets/photo.jpg" alt="photo" class="about__avatar" />
      </div>
    </div>

  </section>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';

@Options({
  name: 'About',
})
export default class About extends Vue {}
</script>

<style lang="scss" scoped>
.about {
  max-width: 1140px;
  background-color: var(--orange-color);

  &__inner {
    padding: 174px 15px 60px;
  }
}
</style>
