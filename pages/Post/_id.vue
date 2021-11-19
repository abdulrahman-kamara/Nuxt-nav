<template>
  <div>
    <h1>{{ post }}</h1>
    <p>{{ description }}</p>
  </div>
</template>
<script>

export default {
  data () {
    return {
      mountains: []
    }
  },
  async fetch () {
    this.mountains = await fetch('https://api.nuxtjs.dev/mountains').then(res => res.json())
  }

}

</script>
