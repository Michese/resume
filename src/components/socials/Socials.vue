<template>
  <div class="socials">
    <ul class="socials__list">
      <li v-for="social in socials" class="socials__item" :key="social.image">
        <a :href="social.link" class="socials__link">
          <img :src="social.image" alt="social" class="socials__image" />
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

@Options({
  name: 'Socials',
})
export default class Socials extends Vue {
  get socials(): { link: string; image: string }[] {
    return [
      {
        link: '#',
        image: githubImage,
      },
      {
        link: '#',
        image: emailImage,
      },
      {
        link: '#',
        image: gmailImage,
      },
      {
        link: '#',
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
