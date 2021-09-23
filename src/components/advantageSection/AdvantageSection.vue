<template>
  <section class="advantage-section">
    <h2 class="advantage-section__section-caption section-caption">{{ advantageSection.caption }}</h2>
    <ul class="advantage-section__list">
      <li class="advantage-section__item">
        <advantage-card
          v-for="advantageCard in advantageSection.list"
          class="advantage-section__advantage-card"
          :advantageCard="advantageCard"
          :key="advantageCard.caption"
        />
      </li>
    </ul>
  </section>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import { Prop } from 'vue-property-decorator';
import { TAdvantageSection } from '@/types';
import AdvantageCard from '@/components/advantageCard/AdvantageCard.vue';

@Options({
  name: 'AdvantageSection',
  components: { AdvantageCard },
})
export default class AdvantageSection extends Vue {
  @Prop({
    type: Object,
    required: true,
  })
  advantageSection!: TAdvantageSection;
}
</script>

<style lang="scss" scoped>
.advantage-section {
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
  align-items: center;
  min-height: 100vh;
  max-width: var(--container-width);
  padding: 30px 15px;
  margin: 0 auto;

  &__section-caption {
    display: block;
    margin-bottom: 26px;
    text-align: center;
  }

  &__advantage-card:not(:last-child) {
    margin-bottom: 27px;
  }
}
</style>
