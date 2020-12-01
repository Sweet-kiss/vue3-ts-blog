<template>  
    <nav class="navbar  navbar-dark bg-primary justify-content-between mb-4 px-4">
      <a class="navbar-brand" href="#">TinaBlog</a>
      <ul v-if="!user.isLogin" class="list-inline mb-0">
          <li class="list-inline-item"><router-link class="btn btn-outline-light my-2">登录</router-link></li>
          <li class="list-inline-item"><router-link class="btn btn-outline-light my-2">注册</router-link></li>
      </ul>
      <ul v-else class="list-inline mb-0">
        <li class="list-inline-item">
          <drop-down :title="`你好 ${user.name}`"></drop-down>
        </li>
      </ul>
    </nav>
  
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue'
import DropDown from './DropDown.vue'

export interface UserProps {
  isLogin: boolean;
  name?: string;
  id?: number;
}

export default defineComponent({
  name: 'GlobalHeader',
  props: {
      user: {
        type: Object as PropType<UserProps>,
        required: true
      }   
  },
  components: {
    DropDown
  },
  setup () {
    //   console.log(user,"ll")
  }
})
</script>

<style>

</style>
