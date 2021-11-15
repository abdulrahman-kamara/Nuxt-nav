<!-- Please remove this file from your project -->
<template>
  <!-- background -->
  <nav class="bg-gray-100">
    <!-- div for the containment area -->
    <div class="  max-auto px-4">
      <!-- div to flex and aspacet -->
      <div class="flex justify-between">
        <!-- nav leftside -->
        <div class="flex space-x-4">
          <logo-menu />
          <nuxt-link
            v-for="{link, title, icon} in links"
            :key="link"
            class="flex items-center space-x-4 text-gray-700 hidden md:flex"
            :to="link"
            :icon="icon"
          >
            {{ title }}
          </nuxt-link>
        </div>
        <!-- navr rightside area -->
        <secondary-nav />
        <!-- mobile button goes here -->
        <div class="md:hidden flex items-center">
          <mobile-button
            :toggle="toggle"
            @toggle="toggle = !toggle"
          />
        </div>
      </div>
      <mobile-menu
        :display="toggle"
        :nav-items="links"
        @toggle="toggle = !toggle"
      />
    </div>
  </nav>
</template>
<script>
import LogoMenu from './template/navigation/LogoMenu.vue'
import SecondaryNav from './template/navigation/SecondaryNav.vue'
import MobileMenu from './template/navigation/MobileMenu.vue'
import MobileButton from './template/navigation/MobileButton.vue'

export default {
  components: {
    LogoMenu,
    SecondaryNav,
    MobileMenu,
    MobileButton

  },
  data () {
    return {
      toggle: false,
      links: [
        { link: '#', title: 'Features', icon: '~/assets/css/image/logo.svg' },
        { link: '#', title: 'Pricing' },
        { link: '#', title: 'Health' },
        { link: '#', title: 'About', icon: '~/assets/css/image/logo.svg' }

      ]
    }
  }
}
</script>
