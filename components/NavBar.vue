<template>
  <section class="nav-bar" :class="{'mobile-menu--open': isMobileMenuOpen}">
    <div class="left">
      <div class="mobile-menu-icon" @click="toggleMobileMenu">
        <MobileMenuIcon/>
      </div>
      <NuxtLink class="logo-container" to="/">
        <img class="logo" src="~/assets/images/logo-mobile.png" width="56" height="46" alt="Logo">
      </NuxtLink>
    </div>

    <div class="center">
      <NuxtLink v-for="link in links" class="nav-link" :to="link.path" :key="link.name">
        {{ link.name }}
      </NuxtLink>
    </div>

    <div class="right">
      <NuxtLink class="nav-icon-link" to="/">
        <SearchIcon/>
      </NuxtLink>
      <NuxtLink class="nav-icon-link" to="/">
        <UserIcon/>
      </NuxtLink>
      <NuxtLink class="nav-icon-link" to="/">
        <ShoppingCartIcon/>
      </NuxtLink>
    </div>


    <div class="mobile-menu__backdrop" ref="backdrop"></div>
    <div class="mobile-menu">
      <button class="mobile-menu__close" @click="closeMobileMenu">
        Close
      </button>
      <div class="mobile-menu__links">
        <NuxtLink v-for="link in links" class="nav-link" :to="link.path" :key="link.name">
          {{ link.name }}
        </NuxtLink>
      </div>
    </div> 
  </section>
</template>

<style lang="scss">
@import '~/assets/scss/nav-bar.scss';
</style>

<script>
import MobileMenuIcon from '~/assets/icons/mobile-menu.svg?inline'
import SearchIcon from '~/assets/icons/search.svg?inline'
import UserIcon from '~/assets/icons/user.svg?inline'
import ShoppingCartIcon from '~/assets/icons/shopping-cart.svg?inline'

export default {
  components: {
    MobileMenuIcon,
    SearchIcon,
    UserIcon,
    ShoppingCartIcon
  },
  data() {
    return {
      isMobileMenuOpen: false,
      links: [
        {
          name: 'Men\'s',
          path: '/'
        },
        {
          name: 'Women\'s',
          path: '/'
        },
        {
          name: 'Accessories',
          path: '/'
        },
        {
          name: 'Sale!',
          path: '/'
        }
      ]
    }
  },
  methods: {
    toggleMobileMenu() {
      this.isMobileMenuOpen = !this.isMobileMenuOpen
    },
    closeMobileMenu() {
      this.isMobileMenuOpen = false
    }
  },
  mounted() {
      this.$refs.backdrop.addEventListener('click', () => {
      this.closeMobileMenu()
    })
  }
}
</script>