<template>
  <div>
    <nav-bar-menu />
    <content-page />
  </div>
</template>

<script>
import ContentPage from '../components/ContentPage.vue'
import NavBarMenu from '../components/NavBarMenu.vue'

export default {
  name: 'Index',
  components: { ContentPage, NavBarMenu }

}
</script>
