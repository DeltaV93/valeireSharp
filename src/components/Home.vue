<template>
  <div>
    <mdc-layout-grid>
      <mdc-layout-cell desktop=1 tablet=12 >
        <!--<flowers></flowers>-->
      </mdc-layout-cell>
      <mdc-layout-cell desktop=4 tablet=12 >
        <div class="fvs--personal-img">
          <img src="https://via.placeholder.com/300x450">
        </div>
      </mdc-layout-cell>
      <mdc-layout-cell desktop=7 tablet=12 class="fvs--intro-box">
        <div>
          <mdc-text
            typo="headline1"
            tag="h1"
            class="text-left">Valerie Sharp</mdc-text>
          <mdc-text
            typo="headline4"
            tag="h2"
            class="text-left">I jump between the <span id="ux-universe" v-on:mouseover="activateUniverseState">UX Universe</span> to <span id="coding-cosmos" v-on:mouseover="activateCosmosState">Coding Cosmos</span> to create user centered digital experiences</mdc-text>
          <mdc-layout-cell desktop=7 tablet=12 class="fvs--intro-box--action">
            <mdc-button @click="$router.push('/work')" raised>View Work</mdc-button>
            <mdc-button @click="Contact" raised>Contact Me</mdc-button>
          </mdc-layout-cell>
        </div>
        <script type="in/Login"></script>
      </mdc-layout-cell>
    </mdc-layout-grid>
  </div>
</template>

<script>
  let _self = this
  export default {
    name: 'Home',
    data () {
      return {
        currentRole: 'Frontend Developer'
      }
    },
    methods: {
      activateUniverseState: function () {
        // console.log(this.$refs)
        console.log(_self)
      },
      activateCosmosState: function () {

      }
    }
  }
</script>

<style scoped>
  .fvs--personal-img {
    /*background-color: #246464;*/
    height: 100%;
    width: 35vw;
    margin-left: 5vw;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  img {
    min-width: 80%;
    height: auto;
    max-height: 850px;
    max-width: 80%;
    left: -8vw;
    position: relative;
    padding-top: 10%;
    /*height: auto;*/
    /*max-width: 50%;*/
    /*opacity: 0.2;*/
  }
  .fvs--personal-img:before {
    content: "\00a0 ";
    position: absolute;
    height: 75%;
    width: 25rem;
    display: block;
    top: 124px;
    /*background-color: #246464;*/
    border: 5px solid #020100;
    z-index: -3;
  }
  .fvs--intro-box h2 {
    background: #fff;
    line-height: 1.5;
  }
</style>
