<template>
  <a href="#" class="advantage-card">
    <header class="advantage-card__header">
      <h3 class="advantage-card__caption">1</h3>
      <strong class="advantage-card__year">2222</strong>
    </header>
    <main class="advantage-card__main">
      <strong class="advantage-card__definition">2222</strong>
      <p class="advantage-card__content">
        Lorem ipsum dolor sit amet, consectetur adipisicing elit. Consequatur deleniti odio repellat tempora temporibus!
        Ad animi beatae cumque deleniti illo illum in magnam nemo nesciunt, officiis quibusdam sequi unde voluptatibus.
      </p>
    </main>
  </a>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import { Prop } from 'vue-property-decorator';

@Options({
  name: 'AdvantageCard',
})
export default class AdvantageCard extends Vue {

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
  }

  &__year {
    font-size: 20px;
    line-height: 1.15em;
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
