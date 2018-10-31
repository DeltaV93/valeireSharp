<template>
  <div>
    <Nav></Nav>
    <div id="app">
      <router-view @contactMe="contactDialog"/>
    </div>

    <mdc-dialog v-model="open"
                title="Please Leave A Message After The Beep."
                accept="Accept"
                cancel="Decline"
                @accept="onAccept"
                @cancel="onDecline">
      <mdc-layout-grid class="contact--form">
        <form width='100px' id='myForm' accept-charset='UTF-8'  enctype='multipart/form-data' action="https://usebasin.com/f/fff111722b3d" method="post">
          <mdc-layout-cell desktop=12>
          <mdc-textfield
            required
            name="name"
            type="text"
            fullwidth
            v-model="name"
            label="Your Name"/>
        </mdc-layout-cell>
          <mdc-layout-cell desktop=12>
            <mdc-textfield  reequired name="email" type="email"fullwidth v-model="email" label="Your Email"/>
          </mdc-layout-cell>
          <mdc-layout-cell desktop="12">
            <mdc-textfield  required name="message" fullwidth v-model="message" label="Enter your message" multiline rows="8" cols="40" />
          </mdc-layout-cell>
        </form>
      </mdc-layout-grid>
    </mdc-dialog>
  </div>

</template>

<script>
  import Nav from '@/components/Nav'
  // import axios from 'axios'
export default {
    name: 'app',
    data () {
      return {
        dialogText: 'Lorem ipsum dolor sit amet, ...',
        open: false,
        name: '',
        email: '',
        message: ''
      }
    },
    components: {
      Nav
    },
    methods: {
      onAccept () {
        console.log('accepted')
        console.log(this.name)
        console.log(this.email)
        console.log(this.message)
        document.getElementById('myForm').submit()
      },
      onDecline () {
        console.log('declined')
      },
      contactDialog () {
        this.open = true
        console.log('open')
        console.log(this.open)
        // return this.open = !this.open
      }
    }
}
</script>

<style>
#app {
  /*text-align: center;*/
  /*padding-top: 60px;*/
}
/*}*/
/*max-width: 730px;*/
/*min-width: 520px;*/
  .contact--form textarea {
      max-width: 730px;
      min-width: 520px;
  }
  form {
    width: 44vw;
  }
</style>
