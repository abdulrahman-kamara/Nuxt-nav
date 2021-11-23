<template>
  <div>
    <nav-bar-menu />
    <div>
      <div id="/index" />
      <div class="flex flex-col px-56 mt-5">
        <h1 class="font-bold text-3xl">
          HOME
        </h1>
        <p>Welcome on home page! </p>
      </div>
    </div>
  </div>
</template>

<script>

import NavBarMenu from '../components/NavBarMenu.vue'

export default {
  name: 'Index',
  components: { NavBarMenu }

}
</script>
