<template>
  <form width='100px' ref='form--contact' id='myForm' accept-charset='UTF-8' >
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
</template>

<script>
  export default {
    name: 'DialogContactForm',
    props: ['formName', 'formEmail', 'formMessage'],
    data () {
      return {
        name: '',
        email: '',
        message: ''
      }
    },
    methods: {
      updateFormData: function (formName, formEmail, formMessage) {
        // this.$emit()
      }
    }
  }
</script>

<style scoped>

</style>
