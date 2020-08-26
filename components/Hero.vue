<template>
  <div>
    <NavBar :is-show-nav-bar="isShowNavBar" />
    <div
      class="hidden lg:w-full lg:flex lg:items-center lg:justify-center h-274"
    >
      <div>
        <a href="#" class="h-157 inline-block my-auto">
          <img
            src="/img/pinup-background/centered-logo.png"
            alt="bg-pinup"
            class="h-full"
          />
        </a>
      </div>
    </div>
    <div id="hero" class="relative lg:h-24 lg:w-full lg:bg-pinup">
      <div class="block">
        <img
          src="/img/pinup-background/pinup-cover__.jpg"
          alt="bg-pinup"
          class="lg:hidden"
        />
      </div>
      <div class="absolute valign mx-auto w-full flex justify-center">
        <div class="w-4/5">
          <a href="#" class="font-vida text-white text-2xl">Home</a>
          <span class="font-vida text-white text-xl">&nbsp;•&nbsp;</span>
          <span class="font-vida text-white text-2xl">Shop</span>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import NavBar from '~/components/NavBar.vue'
export default {
  name: 'Hero',
  components: { NavBar },
  data() {
    return {
      isShowNavBar: false,
    }
  },
  mounted() {
    window.addEventListener('scroll', () => {
      const el = document.querySelector('#hero')
      const elDistanceToTop = el.getBoundingClientRect().top
      if (elDistanceToTop < 0) {
        this.isShowNavBar = true
      } else {
        this.isShowNavBar = false
      }
    })
  },
  methods: {},
}
</script>
