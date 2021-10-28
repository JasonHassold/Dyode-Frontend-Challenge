<template>
  <section class="collection-banner">
    <div class="collection-banner__image">
      <img src="~/assets/images/collection-banner.jpg" width="2160" height="957" loading="lazy" alt="">
    </div>
    <div class="collection-banner__content">
      <h1 class="collection-banner__title">Our Favorite Tees</h1>
      <p class="collection-banner__subtitle">Everyday tees you need!</p>
      <a class="btn">Shop Now</a>
    </div>
  </section>
</template>

<style lang="scss">
@import '~/assets/scss/collection-banner.scss';
</style>

<script>
export default {
  name: 'CollectionBanner'
}
</script>