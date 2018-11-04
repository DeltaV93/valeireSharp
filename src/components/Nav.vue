<template>
  <div id="nav">
    <header class="mdc-top-app-bar ">
      <div class="mdc-top-app-bar__row">
        <section class="mdc-top-app-bar__section mdc-top-app-bar__section--align-start">
          <!--ONLY SHOW ON MOBILE-->
          <!--<a href="#" class="material-icons mdc-top-app-bar__navigation-icon">menu</a>-->
          <span class="mdc-top-app-bar__title">
            <Logo></Logo>
          </span>

        </section>
        <section class="mdc-top-app-bar__section mdc-top-app-bar__section--align-end" role="toolbar">
          <a href="#" class="mdc-top-app-bar__action-item mdc-top-app-bar__action-item-text" aria-label="Work" alt="Work">Work</a>
          <a href="#" class="mdc-top-app-bar__action-item mdc-top-app-bar__action-item-text" aria-label="About Valerie Sharp" alt="About Valerie Sharp">About</a>
          <a href="#" class="mdc-top-app-bar__action-item mdc-top-app-bar__action-item-text" aria-label="Contact Valerie Sharp" alt="Contact Valerie Sharp" @click="contactModal">Contact Me</a>
        </section>
      </div>
    </header>
  </div>

</template>

<script>
  import Logo from '@/components/LogoNew'
  export default {
    name: 'Nav',
    components: {
      Logo
    },
    methods: {
      contactModal: function () {
        this.$emit('contactMe')
      }
    }
  }
</script>

<style scoped>
  #nav{
    padding-bottom: 100px;
    z-index: 10000;
  }
  header {
    z-index: 1;
  }
  .mdc-top-app-bar__title {
    width: 50px;
    height: 50px;
  }
  .mdc-top-app-bar__title svg{
    /*height: 50px;*/
    height: auto;
    width: 100%;
    padding-top: 10px;
  }

  .mdc-top-app-bar__action-item-text {
    width: 110px;
    font-size: 20px;
  }
  .testing .mdc-top-app-bar{

  }
  /*.testing .mdc-top-app-bar a{*/
    /*background-color: transparent;*/
    /*color: #fff;*/
  /*}*/

</style>
