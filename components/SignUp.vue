<template>
  <section class="sign-up">
    <h2 class="sign-up__title"><EmailIcon/> Sign Up & Stay Connected</h2>

    <div class="sign-up__content">
      <p>
        Sign up for the newsletter and get 20% off! Gain access to exclusive 
        offers and be the first to know when new stuff drops!
      </p>

      <div class="sign-up__form">
        <input type="eamil" name="email" placeholder="Enter Your Email Address" />

        <button class="btn">Subscribe</button>
      </div>
    </div>
  </section>
</template>

<style lang="scss">
@import '~/assets/scss/sign-up.scss';
</style>

<script>
import EmailIcon from '~/assets/icons/email.svg?inline'

export default {
  name: 'SignUp',
  components: {
    EmailIcon
  }
}
</script>