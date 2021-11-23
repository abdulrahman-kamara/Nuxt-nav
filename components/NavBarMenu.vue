<!-- Please remove this file from your project -->
<template>
  <!-- background -->
  <nav class="bg-gray-100 filter drop-shadow-lg rounded">
    <!-- div for the containment area -->
    <div class="  max-auto px-4">
      <!-- div to flex and aspacet -->
      <div class="flex justify-between">
        <!-- nav leftside -->
        <div class="flex space-x-4">
          <logo-menu />
          <primary-menu
            v-for="{ link, title, subNavItems } in links"
            id="/events"

            :key="title"
            class="flex items-center space-x-4 text-gray-700 hidden md:flex"
            :link="link"
            :title="title"
            :sub-nav-items="subNavItems"
          />
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
        v-if="toggle"
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
import PrimaryMenu from './template/navigation/PrimaryMenu.vue'

export default {
  name: 'NavBarMenu',
  components: {
    LogoMenu,
    SecondaryNav,
    MobileMenu,
    MobileButton,
    PrimaryMenu

  },
  data () {
    return {
      toggle: false,
      links: [
        { link: '#', title: 'Feature', subNavItems: [{ title: 'coucou' }, { title: 'coucou' }, { title: 'coucou' }] },
        { link: '#', title: 'Pricing' },
        { link: '/event', title: 'Events' },
        { link: '#', title: 'About', subNavItems: [{ title: 'coucou' }] }

      ]
    }
  }
}
</script>
