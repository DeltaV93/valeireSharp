<template>
  <div>
    <Nav></Nav>
    <div id="app">
      <router-view/>
    </div>
  </div>

</template>

<script>
  import Nav from '@/components/Nav'
export default {
    name: 'app',
    components: {
      Nav
    }
}
</script>

<style>
#app {
   /*text-align: center;*/
   /*padding-top: 60px;*/
}
</style>
