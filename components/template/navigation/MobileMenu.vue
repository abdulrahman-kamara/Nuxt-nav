<template>
  <div v-if="display" class="mobile-menu">
    <nuxt-link
      v-for="{link, title, icon} in navItems"
      :key="link"
      :to="link"
      :icon="icon"
      class="block py-2 px-2 md:hidden"
    >
      {{ title }}
    </nuxt-link>
  </div>
</template>
<script>

export default {
  name: 'MobileMenu',
  props: {
    display: {
      type: Boolean,
      default: false
    },
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
