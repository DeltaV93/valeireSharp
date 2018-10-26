<template>
  <div>
    <Nav></Nav>
    <div id="app">
      <router-view/>
    </div>

    <mdc-dialog v-model="open"
                title="Title"
                accept="Accept"
                cancel="Decline"
                @accept="onAccept"
                @cancel="onDecline">
      {{ dialogText }}
    </mdc-dialog>
  </div>

</template>

<script>
  import Nav from '@/components/Nav'
export default {
    name: 'app',
    data () {
      dialogText: 'Lorem ipsum dolor sit amet, ...',
      open: false,
    },
    components: {
      Nav
    },
    methods: {
      onAccept () {
        console.log('accepted')
      },
      onDecline () {
        console.log('declined')
      }
  }
}
</script>

<style>
#app {
   /*text-align: center;*/
   /*padding-top: 60px;*/
}
</style>
