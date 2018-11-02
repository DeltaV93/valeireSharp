<template>
  <div>
    <Nav @contactMe="contactDialog"></Nav>
    <div id="app">
      <router-view @contactMe="contactDialog"/>
    </div>

    <mdc-dialog  v-model="open"
                title="Please Leave A Message After The Beep."
                accept="Accept"
                cancel="Decline"
                @validate="onAccept"
                @cancel="onDecline">
      <mdc-layout-grid class="contact--form">
        <form v-if='contactResponseMsg === "sendMessage"' width='100px' id='myForm' accept-charset='UTF-8' >
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
        <div v-if='contactResponseMsg === "thankYouMessage"'>

        </div>
      </mdc-layout-grid>
    </mdc-dialog>
  </div>

</template>

<script>
  import Nav from '@/components/Nav'
  import axios from 'axios'
export default {
    name: 'app',
    data () {
      return {
        dialogText: 'Lorem ipsum dolor sit amet, ...',
        open: false,
        name: '',
        email: '',
        message: '',
        contactResponseMsg: 'sendMessage'
      }
    },
    components: {
      Nav
    },
    methods: {
      onAccept (e) {
        console.log('accepted')
        console.log(this.name)
        console.log(this.email)
        console.log(this.message)

        axios.post('https://api.formbucket.com/f/buk_OikQqv7vThABOKEP9WyH7dQl', {
          name: this.name,
          email: this.email,
          message: this.message
        })
          .then(function (response) {
            let data = response.data
            if (data.id) {
              console.log(response)
            } else {
              alert('message did not send')
            }

          })
          .catch(function (error) {
            console.log(error)
          })
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
