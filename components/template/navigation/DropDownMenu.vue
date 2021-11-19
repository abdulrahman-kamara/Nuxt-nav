<template>
  <div class="">
    <ul class="absolute  mt-12 py-2 px-2 bg-white rounded-lg justify-center left-30 shadow-2xl transition ease-in duration-700 flex flex-col">
      <li
        v-for="{ titre} in dropmenu"
        :key="titre"
        class="p-2 w-56 min-w-full  flex justify-center hover:text-white hover:bg-gray-900 hover:rounded-2xl"
        :link="link"
      >
        {{ titre }}
      </li>
    </ul>
  </div>
</template>
<script>

export default {
  name: 'DropDownMenu',
  props: {
    title: {
      type: String,
      default: ''
    },
    link: {
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
      dropmenu: [
        { link: '#', titre: 'Post' },
        { link: '#', titre: 'Article' },
        { link: '#', titre: 'Costumes' },
        { link: '#', titre: 'FAQ' }
      ]
    }
  }

}
</script>
