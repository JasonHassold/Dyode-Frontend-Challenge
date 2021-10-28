<template>
  <section class="collections">
    <div class="collections__card">
      <img src="~/assets/images/Womens Image.jpg" width="653" height="854" alt="">

      <NuxtLink to="/">Women's</NuxtLink>
    </div>

    <div class="collections__card">
      <img src="~/assets/images/Mens Image.jpg" width="653" height="854" alt="">

      <NuxtLink to="/">Men's</NuxtLink>
    </div>

    <div class="collections__card">
      <img class="img--desktop" src="~/assets/images/Accessories Image.jpg" 
        width="653" height="854" alt="">
      <img class="img--mobile" src="~/assets/images/Accessories Image Mobile.jpg" 
        width="670" height="406" alt="">

      <NuxtLink to="/">Accessories</NuxtLink>
    </div>
  </section>
</template>

<style lang="scss">
@import '~/assets/scss/collections.scss';
</style>

<script>
export default {
  name: 'Collections'
}
</script>