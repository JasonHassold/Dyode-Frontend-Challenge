<template>
  <section class="collection-slider">
    <h2><span>Shop </span>New Arrivals</h2>

    <div class="splide" ref="splide">
      <div class="splide__arrows">
        <button class="splide__arrow splide__arrow--prev">
          <ArrowIcon/>
        </button>
        <button class="splide__arrow splide__arrow--next">
          <ArrowIcon/>
        </button>
      </div>

      <div class="splide__track">
        <div class="splide__list">
          <div v-for="i in 8" class="splide__slide" :key="i">
            <NuxtLink class="product-card" to="/" >
              <div class="product-card__image">
                <img :src="product.image.src" :width="product.image.width" 
                  :height="product.image.height" alt="">
              </div>
              <div class="product-card__info">
                <p class="product-card__title">
                  {{ product.title }}
                </p>
                <p class="product-card__type">
                  {{ product.type }}
                </p>
                <div class="product-card__price">
                  {{ product.price }}
                </div>
              </div>
            </NuxtLink>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style lang="scss">
@import '~/assets/scss/collection-slider.scss';
</style>

<script>
import Splide from '@splidejs/splide'
import ArrowIcon from '~/assets/icons/arrow.svg?inline'

export default {
  name: 'CollectionSlider',
  components: {
    ArrowIcon,
  },
  data () {
    return {
      splide: null,
      product: {
        image: {
          src: require('~/assets/images/Product.jpg'),
          width: 560,
          height: 842,
        },
        title: 'Product Title',
        type: 'Women\'s T-Shirt',
        price: '$19.99'
      },
    }
  },
  mounted() {
    this.splide = new Splide(this.$refs.splide, {
      perPage: 4,
      gap: '20px',
      pagination: false,
      breakpoints: {
        768: {
          perPage: 2,
          gap: '10px',
        },
      }
    }).mount()
  }
}
</script>