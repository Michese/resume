<template>
  <footer class="footer-page">
    <socials class="footer-page__socials" />
  </footer>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import Socials from '@/components/socials/Socials.vue';

@Options({
  name: 'FooterPage',
  components: { Socials }
})
export default class FooterPage extends Vue {

}
</script>

<style lang="scss" scoped>
.footer-page {
  display: flex;
  justify-content: center;
  max-width: var(--container-width);
  padding: 30px 15px 60px;
  margin: 0 auto;

  &__socails {

  }
}
</style>
