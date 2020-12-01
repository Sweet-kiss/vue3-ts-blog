<template>
  <div class="row">
   <div class="col-4 mb-4" v-for="item in columnList" :key="item.id">
    <div class="card h-100 shadow-sm">        
        <div class="card-body  text-center">
            <img :src="item.avatar" class="rounded-circle border border-light my-3" alt="...">
            <h5 class="card-title">{{item.title}}</h5>
            <p class="card-text">{{item.description}}</p>
            <a href="#" class="btn btn-primary">进入专栏</a>
        </div>
    </div>
   </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

interface ColumnProps {
   id: number;
   avatar: string;
   title: string;
   description: string;
}

export default defineComponent({
  name: 'App',
  components: {},
  setup () {
    const columnList: ColumnProps[] = [
        {
            id:1,
            avatar: 'http://vue-maker.oss-cn-hangzhou.aliyuncs.com/vue-marker/5ee22dd58b3c4520912b9470.jpg?x-oss-process=image/resize,m_pad,h_100,w_100',
            title: '作者01',
            description: '这是的test1专栏，有一段非常有意思的简介，可以更新一下欧'
        },
        {
            id:2,
            avatar: 'http://vue-maker.oss-cn-hangzhou.aliyuncs.com/vue-marker/5ee22dd58b3c4520912b9470.jpg?x-oss-process=image/resize,m_pad,h_100,w_100',
            title: '作者02',
            description: '这是的test1专栏，有一段非常有意思的简介，可以更新一下欧'
        },
        {
            id:3,
            avatar: 'http://vue-maker.oss-cn-hangzhou.aliyuncs.com/vue-marker/5ee22dd58b3c4520912b9470.jpg?x-oss-process=image/resize,m_pad,h_100,w_100',
            title: '作者03',
            description: '这是的test1专栏，有一段非常有意思的简介，可以更新一下欧'
        }        
    ]
    return {
       columnList
    }
  }
})
</script>

<style>
.card-body img {
  width: 50px;
  height: 50px;
}
</style>
