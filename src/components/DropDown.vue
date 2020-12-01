<template>
  <div class="dropdown" ref="dropdownRef">
        <a href="#" class="btn btn-outline-light my-2 dropdown-toggle" @click.prevent="toggle">
           {{title}}
        </a>
        <div class="dropdown-menu" :style="{display: 'block'}" v-if="isOpen">
        <a class="dropdown-item" href="#">新建文章</a>
        <a class="dropdown-item disabled" href="#">编辑资料</a>
         <a class="dropdown-item"  href="#">推出登录</a>
      </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref, onMounted, onUnmounted, watch } from 'vue'
import useClickOutside from '../hooks/useClickOutside'

export default defineComponent({
  name: 'DropDown',
  props: {
     title: {
         type: String,
         require: true
     }
  },
  setup () {
    const isOpen = ref(false)
    const dropdownRef = ref<null | HTMLElement>(null)
    const toggle = () => {
        isOpen.value = !isOpen.value
    }
    const isClickOutside = useClickOutside(dropdownRef)
  
    watch (isClickOutside, () => {
      if(isOpen.value && isClickOutside.value) {
          isOpen.value = false
      }
    })  
    return {
        isOpen,
        toggle,
        dropdownRef
    }
  }
})
</script>

<style>
.disabled {
  color: #6c757d;
  pointer-events: none;
  background-color: transparent;
}
</style>
