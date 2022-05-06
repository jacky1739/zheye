<template>
  <div class="dropdown">
    <a href="#" class="btn btn-outline-light my-2 dropdown-toggle">{{ title }}</a>
    <ul class="dropdown-menu" :style="{ display: 'block' }">
        <li class="dropdown-item">
            <a href="#">新建文章</a>
        </li>
        <li class="dropdown-item">
            <a href="#">編輯資料</a>
        </li>
    </ul>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
export default defineComponent({
  name: 'dropdown',
  props: {
    title: {
      type: String,
      required: true
    }
  }
})
</script>
