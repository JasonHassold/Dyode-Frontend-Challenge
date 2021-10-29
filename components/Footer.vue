<template>
  <section class="footer">
    <div class="footer__linklist-container">
      <div v-for="linklist in linklists" :key="linklist.header">
        <div class="footer__linklist-header" @click="toggleCollapse">{{ linklist.header }} <span>+</span></div>
        <ul class="footer__linklist">
          <li v-for="link in linklist.links" class="footer__link" :key="link.text">
            <NuxtLink :to="link.path">
              {{ link.text }}
            </NuxtLink>
          </li>
        </ul>
      </div>
    </div>

    <div class="footer__social-links-container">
      <div class="footer__social-links-header">
        Follow Us
      </div>

      <div class="footer__social-links">
        <a href="/">
          <FacebookIcon/>
        </a>
        <a href="/">
          <InstagramIcon/>
        </a>
        <a href="/">
          <TwitterIcon/>
        </a>
      </div>
    </div>
  </section>
</template>

<style lang="scss">
@import '~/assets/scss/footer.scss';
</style>

<script>
import FacebookIcon from '~/assets/icons/facebook.svg?inline'
import InstagramIcon from '~/assets/icons/instagram.svg?inline'
import TwitterIcon from '~/assets/icons/twitter.svg?inline'

export default {
  name: 'Footer',
  components: {
    FacebookIcon,
    InstagramIcon,
    TwitterIcon
  },
  data() {
    return {
      linklists: [
        {
          header: 'Customer Service',
          links: [
            {
              text: 'Accessibility',
              path: '/',
            },
            {
              text: 'Contact Us',
              path: '/',
            },
            {
              text: 'Return Policy',
              path: '/',
            },
            {
              text: 'FAQ',
              path: '/',
            },
            {
              text: 'Gift Certificates',
              path: '/',
            },
            {
              text: 'Wishlist',
              path: '/',
            },
          ],
        },
        {
          header: 'Company',
          links: [
            {
              text: 'About Us',
              path: '/',
            },
            {
              text: 'Careers',
              path: '/',
            },
            {
              text: 'Press',
              path: '/',
            },
            {
              text: 'Affiliates',
              path: '/',
            },
          ],
        },
      ]
    }
  },
  methods: {
    toggleCollapse(e) {
      if (window.innerWidth < 576) {
        const target = e.currentTarget
        const linklist = target.nextElementSibling

        if (linklist.style.maxHeight === '') {
          linklist.style.maxHeight = linklist.scrollHeight + 'px'
          target.children[0].textContent = '-'
        } else {
          linklist.style.maxHeight = ''
          target.children[0].textContent = '+'
        }
      }
    }
  }
}
</script>