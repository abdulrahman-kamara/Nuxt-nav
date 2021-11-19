<template>
  <div class="md:flex">
    <div class="md:flex-shrink-0">
      {{ product.name }}
    </div>
    <div class="mt-4 md:mt-0 md:ml-6">
      <div class="text-indigo-600 text-sm text-4xl">
        {{ product.sort }}
      </div>
      <NuxtLink
        :to="product.slug"
        class="block mt-1 text-lg hover:underline text-gray-900"
      >
        {{ product.name }}
      </NuxtLink>
      <p class="mt-2 text-gray-900">
        {{ product.label }}
      </p>
    </div>
  </div>
</template>
<script>

export default {
  name: 'Events',
  props: {
    product: {
      type: Object,
      default: () => {}
    }
  }
  //   async asyncData ({ $axios }) {
  //     const { data: { events = [] } } = await $axios.$get(
  //       'https://api.demo.politic-us.com/api/v1/devices/fetch-all',
  //       { headers: { Authorization: 'Bearer ouolRPiyFBRe1P9TIge7.nkXZmJnT3Ol6jU0RPanl' } }
  //     )
  //     return { events }
  //   },

}

</script>
