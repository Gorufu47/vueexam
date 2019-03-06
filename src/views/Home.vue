<template>
  <div class="home">
    <!-- <img alt="Vue logo" src="../assets/logo.png"> -->
    <!-- <HelloWorld></HelloWorld> -->
    <Show></Show>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import Show from '@/components/show.vue'


export default {
  name: 'home',
  components: {
    HelloWorld,
    Show
  }
}
</script>
