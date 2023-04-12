<template>
  <button @click="increment">
    {{ state.count }}
  </button>
  <p v-show="isShow">{{isShow?'展示':'不展示'}}</p>

  <!-- <div @click="doEvent('hello',$event)">事件处理</div> -->
  <div @click="(event=>doEvent('hello',event))">事件处理</div>
  <!-- 不传递参数的时候 @click="event" 和@click="event()" 好像没什么区别 ，
  看下vue的模板编译，处理事件这块；方法事件处理器/内联事件处理器-->
</template>

<script setup>
import { reactive ,ref} from 'vue'

const state = reactive({ count: 0 })
const isShow = ref(false)
const num = ref(0)
function increment() {
    isShow.value = !isShow.value
    state.count++
}
function doEvent(msg,event){
    console.log('1111111111',msg,event)
}
</script>