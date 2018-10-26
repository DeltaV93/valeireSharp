<template>
  <div id="nav">
    <header class="mdc-top-app-bar">
      <div class="mdc-top-app-bar__row">
        <section class="mdc-top-app-bar__section mdc-top-app-bar__section--align-start">
          <a href="#" class="material-icons mdc-top-app-bar__navigation-icon">menu</a>
          <span class="mdc-top-app-bar__title"><Logo></Logo></span>
        </section>
      </div>
    </header>
  </div>

</template>

<script>
  import Logo from '@/components/Logo'
  export default {
    name: 'Nav',
    components: {
      Logo
    }
  }
</script>

<style scoped>
  #nav{
    padding-bottom: 120px;
  }
  .mdc-top-app-bar__title img{
    width: 100%;

  }
</style>
