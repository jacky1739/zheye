<template>
  <div class="container">
    <global-header :user="currentUser"></global-header>
    <column-list :list="testData"></column-list>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import ColumnList, { ColumnProps } from './components/ColumnList.vue'
import GlobalHeader, { UserProps } from './components/GlobalHeader.vue'

const currentUser: UserProps = {
  isLogin: true,
  name: 'jacky'
}

const testData: ColumnProps[] = [
  {
    id: 1,
    title: 'test1的專欄',
    description: '這是test1專欄, 有一段非常有意思的簡介, 可以更新一下歐',
    avatar: 'https://avatars.githubusercontent.com/u/6128107?s=280&v=4'
  },
  {
    id: 2,
    title: 'test2的專欄',
    description: '這是test2專欄, 有一段非常有意思的簡介, 可以更新一下歐'
    // avatar: 'https://avatars.githubusercontent.com/u/6128107?s=280&v=4'
  },
  {
    id: 3,
    title: 'test3的專欄',
    description: '這是test3專欄, 有一段非常有意思的簡介, 可以更新一下歐',
    avatar: 'https://avatars.githubusercontent.com/u/6128107?s=280&v=4'
  },
  {
    id: 4,
    title: 'test4的專欄',
    description: '這是test4專欄, 有一段非常有意思的簡介, 可以更新一下歐',
    avatar: 'https://avatars.githubusercontent.com/u/6128107?s=280&v=4'
  }
]

export default defineComponent({
  name: 'App',
  components: {
    ColumnList, GlobalHeader
  },
  setup () {
    return {
      testData, currentUser
    }
  }
})
</script>

<style>

</style>
