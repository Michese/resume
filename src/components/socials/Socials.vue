<template>
  <div class="socials">
    <ul class="socials__list">
      <li v-for="social in socials" class="socials__item" :key="social.image">
        <a :href="social.link" class="socials__link" target="_blank">
          <img :src="social.image" alt="social" class="socials__image" :class="{inHeader: 'socials__image_size_s'}" />
        </a>
      </li>
    </ul>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import githubImage from './assets/github.svg';
import emailImage from './assets/email.svg';
import gmailImage from './assets/gmail.svg';
import vkImage from './assets/vk.svg';
import { Prop } from 'vue-property-decorator';

@Options({
  name: 'Socials',
})
export default class Socials extends Vue {
  @Prop({
    type: Boolean,
    required: false,
    default: () => false,
  })
  inHeader!: boolean;

  get socials(): { link: string; image: string }[] {
    return [
      {
        link: 'https://github.com/michese',
        image: githubImage,
      },
      {
        link: 'mailto:michese48@mail.ru',
        image: emailImage,
      },
      {
        link: 'mailto:michese48@gmail.com',
        image: gmailImage,
      },
      {
        link: 'https://vk.com/michese',
        image: vkImage,
      },
    ];
  }
}
</script>

<style lang="scss" scoped>
.socials {
  &__list {
    display: flex;
  }

  &__item:not(:last-child) {
    margin-right: 30px;
  }
}
</style>
