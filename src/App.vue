<template>
  <div id="app" class="flex container h-screen w-full">
    <SideNav />
    <Tweets />
    <Trendings />
    
  </div>
</template>

<script>
import SideNav from './components/SideNav.vue'
import Tweets from './components/Tweets.vue'
import Trendings from './components/Trendings.vue'

export default {
  name: 'App',
  components: {
    SideNav,
    Tweets,
    Trendings,
  },
}
</script>

<style>

</style>
