<template>
  <div class="dropdown" ref="dropdownRef">
    <a href="#" class="btn btn-outline-light my-2 dropdown-toggle" @click.prevent="toggleOpen">{{ title }}</a>
    <ul class="dropdown-menu" :style="{ display: 'block' }" v-if="isOpen">
      <slot></slot>
    </ul>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref, watch } from 'vue'
import useClickOutside from '../hooks/useClickOutside'

export default defineComponent({
  name: 'dropdown',
  props: {
    title: {
      type: String,
      required: true
    }
  },
  setup () {
    const isOpen = ref(false)

    const dropdownRef = ref<null | HTMLElement>(null) // 宣告為一個聯合類型和return就可以取得DOM的節點
    const isClickOutside = useClickOutside(dropdownRef)
    watch(isClickOutside, () => {
      if (isOpen.value && isClickOutside.value) {
        isOpen.value = !isOpen.value
      }
    })

    const toggleOpen = () => {
      isOpen.value = !isOpen.value
    }

    return {
      isOpen, toggleOpen, dropdownRef
    }
  }
})
</script>
