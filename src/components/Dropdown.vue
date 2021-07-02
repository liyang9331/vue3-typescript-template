<template>
  <div class="dropdown">
    <a href="#" class="my-2 dropdown-toggle" @click.prevent="toggleOpen">
      {{title}}
    </a>
  <ul class="dropdown-menu" :style="{display :'block'}" v-if="isOpen" aria-labelledby="dropdownMenuButton1">
    <li><a class="dropdown-item" href="#">Action</a></li>
    <li><a class="dropdown-item" href="#">Action</a></li>
    <li><a class="dropdown-item" href="#">Action</a></li>
  </ul>
</div>
</template>
<script lang="ts">
import { defineComponent, ref } from 'vue';
export default defineComponent({
  name: 'Dropdown',
  props: {
    title: {
      type: String,
      required: true
    }
  },
  setup () {
    const isOpen = ref(false);
    const toggleOpen = () => {
      isOpen.value = !isOpen.value
    }
    return {
      isOpen,
      toggleOpen
    }
  }
})
</script>
<style scoped>
</style>
