<script setup lang="ts">
import { ref,  onMounted } from 'vue';
import { useHelleWorld } from '@/store/helloworld'
const helloWorldStore = useHelleWorld()
defineProps<{ msg: string }>()
const msg = ref('Hello World!')
const count = ref(0)
const env =  import.meta.env.VITE_BASEURL
onMounted(() => {
  console.log(console.log(import.meta.env.VITE_BASEURL))
})
</script>

<template>
  <h1>{{ msg }}</h1>
  <h2>环境变量：{{ env }}</h2>
  <h2>store：{{ helloWorldStore.message }}</h2>
  <div class="card">
    <button type="button" @click="count++">count is {{ count }}</button>
    <p>
      Edit
      <code>components/HelloWorld.vue</code> to test HMR
    </p>
  </div>

  <p>
    Check out
    <a href="https://vuejs.org/guide/quick-start.html#local" target="_blank"
      >create-vue</a
    >, the official Vue + Vite starter
  </p>
  <p>
    Install
    <a href="https://github.com/vuejs/language-tools" target="_blank">Volar</a>
    in your IDE for a better DX
  </p>
  <p class="read-the-docs">Click on the Vite and Vue logos to learn more</p>
  <div  class="read-the-docs">
    <div class="read">
      vite vue less
    </div>
  </div>
</template>

<style scoped lang="less">
.read-the-docs {
  color: #888;
  .read{
    background: red;
  }
}
</style>
@/store/helloworld