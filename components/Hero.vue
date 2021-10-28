<template>
  <section class="hero">
    <div class="splide" ref="splide">
      <div class="splide__track">
        <div class="splide__list">
          <div v-for="content in slideContents" class="splide__slide">
            <img :src="content.image.src" alt=""
              :width="content.image.width" :height="content.image.height">

            <div class="content" :class="[`text-${content.textColorOverImg}`]">
              <h1>{{ content.title }}</h1>
              <p>{{ content.subtitle }}</p>
              <NuxtLink class="btn" :to="content.linkPath">
                Shop Now
              </NuxtLink>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style lang="scss">
@import '~/assets/scss/hero.scss';
</style>

<script>
import Splide from '@splidejs/splide'

export default {
  name: 'Hero',
  data() {
    return {
      splide: null,
      slideContents: [
        {
          image: {
            src: require('~/assets/images/hero-1.jpg'),
            width: 2161,
            height: 957,
          },
          textColorOverImg: 'green',
          title: 'Shop New Arrivals',
          subtitle: 'Our coolest new items are waiting for you!',
          linkPath: '/',
        },
        {
          image: {
            src: require('~/assets/images/hero-2.jpg'),
            width: 2161,
            height: 957,
          },
          textColorOverImg: 'white',
          title: 'Our Fave Tees',
          subtitle: 'Shop all of our favorites.',
          linkPath: '/',
        },
        {
          image: {
            src: require('~/assets/images/hero-3.jpg'),
            width: 2161,
            height: 957,
          },
          textColorOverImg: 'white',
          title: 'Men’s Tees',
          subtitle: 'Find the perfect shirt.',
          linkPath: '/',
        }
      ]
    }
  },
  mounted() {

    this.splide = new Splide(this.$refs.splide, {
      arrows: false,
      type: 'loop',
      rewind: true,
      perPage: 1,
      gap: '0',
    }).mount()

  }
}
</script>