<template>
  <a
    class="advantage-card"
    :href="advantageCard.link"
    :download="advantageCard.isDownload"
    :target="advantageCard.isDownload ? '_self' : '_blank'"
  >
    <header class="advantage-card__header">
      <h3 class="advantage-card__caption">{{ advantageCard.caption }}</h3>
      <strong class="advantage-card__year">{{ advantageCard.year }}</strong>
    </header>
    <main class="advantage-card__main">
      <strong class="advantage-card__definition">{{ advantageCard.definition }}</strong>
      <p class="advantage-card__content">{{ advantageCard.content }}</p>
    </main>
  </a>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import { Prop } from 'vue-property-decorator';
import { TAdvantageCard } from '@/types';

@Options({
  name: 'AdvantageCard',
})
export default class AdvantageCard extends Vue {
  @Prop({
    type: Object,
    required: true,
  })
  advantageCard!: TAdvantageCard;
}
</script>

<style lang="scss" scoped>
.advantage-card {
  display: block;
  background: #fff;
  box-shadow: 5px 5px 15px 5px rgba(0, 0, 0, 0.25);
  border-radius: 30px;

  &__header {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    min-height: 120px;
    background-color: var(--orange-color);
    border-radius: 30px 30px 0 0;
  }

  &__caption {
    font-weight: 700;
    font-size: 23px;
    margin-bottom: 20px;
    color: #fff;
  }

  &__year {
    font-size: 20px;
    line-height: 1.15em;
    color: #fff;
  }

  &__main {
    padding: 32px 60px;
  }

  &__definition {
    display: block;
    margin-bottom: 25px;
    font-weight: 700;
    font-size: 20px;
    line-height: 1.15em;
    text-align: center;
  }

  &__content {
    font-size: 18px;
    line-height: 1.444444em;
  }
}
</style>
