<template>
  <div class="mobile-menu">
    <nuxt-link
      v-for="{link, title} in navItems"
      :key="title"
      :to="link"
      class="block py-2 px-2 md:hidden hover:text-white hover:bg-gray-900 hover:rounded-sm"
    >
      {{ title }}
    </nuxt-link>
  </div>
</template>
<script>

export default {
  name: 'MobileMenu',
  props: {
    navItems: {
      type: Array,
      default: () => []
    }
  },
  methods: {
    navigate (link) {
      this.$router.push(link)
      this.$emit('toggle')
    }
  }
}
</script>
