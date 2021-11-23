<template>
  <div>
    <nav-bar-menu />

    <div id="events" class="md:grid grid-cols-4 ">
      <div
        v-for="{description, name, content} in events"
        :key="name"
        :name="name"
        :content="content"
        :description="description"
        class="border-2 rounded-lg p-2 "
      >
        <div class="mt-4 md:mt-0 md:ml-6 bg-white">
          <div class="text-indigo-600 text-sm text-3xl">
            <h1>{{ name }}</h1>
          </div>
          <div class="md:flex-shrink-0">
            {{ content }}
          </div>
          <p class="mt-2 text-gray-900">
            {{ description }}
          </p>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import NavBarMenu from '../components/NavBarMenu.vue'

export default {
  name: 'Events',
  components: { NavBarMenu },

  async asyncData ({ $axios }) {
    const { data: { events = [] } } = await $axios.$get('https://api.demo.politic-us.com/api/v1/devices/fetch-all',
      { headers: { Authorization: 'Bearer ouolRPiyFBRe1P9TIge7.nkXZmJnT3Ol6jU0RPanl' } })

    return { events }
  }
}

</script>
