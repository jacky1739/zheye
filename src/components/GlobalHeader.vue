<template>
  <nav class="navbar navbar-dark bg-primary justify-content-between mb-4 px-4">
    <a class="navbar-brand" href="#">者也專欄</a>
    <ul v-if="!user.isLogin" class="list-inline mb-0 d-flex">
        <li class="list-inline-item">
            <a class="btn btn-outline-light my-2" href="#">登入</a>
        </li>
        <li>
            <a class="btn btn-outline-light my-2" href="#">註冊</a>
        </li>
    </ul>
    <ul v-else class="list-inline mb-0">
      <li>
        <dropdown :title="`你好 ${ user.name }`"></dropdown>
      </li>
    </ul>
  </nav>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue'
import Dropdown from './Dropdown.vue'

export interface UserProps {
  isLogin: boolean
  name?: string
  id?: number
}

export default defineComponent({
  name: 'GlobalHearder',
  components: {
    Dropdown
  },
  props: {
    user: {
      type: Object as PropType<UserProps>,
      required: true
    }
  }
})
</script>
