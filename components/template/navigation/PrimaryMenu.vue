<template>
  <nuxt-link class="relative" :to="link">
    {{ title }}
    <button class="button" @click="dropdown">
      <svg
        v-if="subNavItems && subNavItems.length"
        xmlns="http://www.w3.org/2000/svg"
        class="h-6 w-full inline items-center animate-bounce"
        fill="none"
        viewBox="0 0 24 24"
        stroke="currentColor"
      >
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7" />
      </svg>
    </button>
    <drop-down-menu
      v-if="toggle"
      :sub-nav-items="subNavItems"
      @toggle="toggle = !toggle"
    />
  </nuxt-link>
</template>
<script >
import DropDownMenu from './DropDownMenu.vue'
export default {
  components: {
    DropDownMenu
  },
  props: {
    links: {
      type: Array,
      default: () => []
    },
    link: {
      type: String,
      default: ''
    },
    title: {
      type: String,
      default: ''
    },
    dropmenu: {
      type: String,
      default: ''
    },
    subNavItems: {
      type: Array,
      default: () => []
    }

  },
  data () {
    return {
      toggle: false
    }
  },
  methods: {
    dropdown () {
      this.toggle = !this.toggle
    }
  }
}
</script>
