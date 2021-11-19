<template>
  <div class=" min-h-screen p-10 text-center bg-yellow-300">
    <div class=" md:grid md:grid-cols-2 2xl:flex  sm:space-y-0 md:justify-center">
      <div>
        <event-page
          v-for="event in events"
          :key="event.name"
          :product="event"
        />
      </div>
    </div>
  </div>
</template>
<script>

import EventPage from './template/navigation/Events/EventPage.vue'

export default {

  components: {
    EventPage

  },
  async asyncData ({ $axios }) {
    const { data: { events = [] } } = await $axios.$get('https://generator.politic-us.com/events?preview=true', { headers: { Authorization: 'Bearer ouolRPiyFBRe1P9TIge7.nkXZmJnT3Ol6jU0RPanl' } })
    return { events }
  },
  data () {
    return {
      events: []
    }
  }

}

</script>
