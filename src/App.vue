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
        <form width='100px' ref='form--contact' id='form--contact' accept-charset='UTF-8' >
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
        <!--<component-->
          <!--:formName='name'-->
          <!--:formEmail='email'-->
          <!--:formMessage='message'-->
          <!--v-bind:is="contactMsgComponent"-->
          <!--class="tab"-->
        <!--&gt;</component>-->

      </mdc-layout-grid>
    </mdc-dialog>
  </div>

</template>

<script>
  import Nav from '@/components/Nav'
  import DialogContactForm from '@/components/DialogContactForm'
  import DialogContactSuccess from '@/components/DialogContactSuccess'
  import DialogContactError from '@/components/DialogContactError'

  import axios from 'axios'
  const self = this
export default {
    name: 'app',
    data () {
      return {
        dialogText: 'Lorem ipsum dolor sit amet, ...',
        open: false,
        name: '',
        email: '',
        message: '',
        contactMsgComponent: 'DialogContactForm'
      }
    },
    components: {
      Nav,
      DialogContactForm,
      DialogContactSuccess,
      DialogContactError
    },
    methods: {
      onAccept () {
        let dialogHeader = document.getElementsByClassName('mdc-dialog__header__title')[0]
        let dialogBody = document.getElementsByClassName('mdc-dialog__body')[0]
        let dialogAcceptBtn = document.getElementsByClassName('mdc-dialog__footer__button--accept')[0]
        let dialogThankYouBodyMsg = '<div class="mdc-layout-cell mdc-layout-grid__cell mdc-layout-grid__cell--span-12-tablet mdc-layout-grid__cell--span-12-desktop"><h3> Please give me 24 hours to come up with a thoughtful response</h3></div>'

        axios.post('https://api.formbucket.com/f/buk_OikQqv7vThABOKEP9WyH7dQl', {
          name: this.name,
          email: this.email,
          message: this.message
        })
          .then(function (response) {
            let data = response.data
            if (data.id) {
              console.log('message sent')
              dialogHeader.innerText = 'Your Message was sent!'
              dialogBody.innerHTML = dialogThankYouBodyMsg
              dialogAcceptBtn.style.visibility = 'hidden'
            } else {
              self.contactResponseMsg = 'DialogContactError'
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
        self.contactResponseMsg = 'sendMessage'
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
