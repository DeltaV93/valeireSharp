<template>
  <div id="fvs--home" ref="hero">
    <mdc-layout-grid>
      <mdc-layout-cell desktop=1 tablet=12 >
        <!--<flowers></flowers>-->
      </mdc-layout-cell>
      <mdc-layout-cell desktop=4 tablet=12 >
        <div class="fvs--personal-img">
          <!-- 300x350 -->
          <img src="https://via.placeholder.com/300x350">
        </div>
      </mdc-layout-cell>
      <mdc-layout-cell desktop=7 tablet=12 class="fvs--intro-box">
        <div>
          <mdc-text
            typo="headline1"
            tag="h1"
            class="text-left">Valerie Sharp</mdc-text>
          <mdc-text
            typo="headline5"
            tag="h2"
            class="text-left">I jump between the <span id="ux-universe" v-on:mouseover="activateUniverseState">UX Universe</span> to <span id="coding-cosmos" v-on:mouseover="activateCosmosState">Coding Cosmos</span> to create user centered digital experiences</mdc-text>
          <mdc-layout-cell desktop=7 tablet=12 class="fvs--intro-box--action">
            <mdc-button @click="$router.push('/work')" raised>View Work</mdc-button>
            <!--<mdc-button @click="Contact" raised>Contact Me</mdc-button>-->
          </mdc-layout-cell>
        </div>
        <script type="in/Login"></script>
      </mdc-layout-cell>
    </mdc-layout-grid>

    <section class="fvs--my-process" ref="my-process">
      <mdc-layout-grid>
        <mdc-layout-cell desktop=12 tablet=12>
          <h1 class="text-center">My Process</h1>
          <h2>From gathering bossiness requirements to pushing to productions</h2>
        </mdc-layout-cell>

        <mdc-layout-cell desktop=12>
          <mdc-grid-list with-support-text interactive>
            <mdc-grid-tile ratio="16x9"
                           v-for="(item, index) in process" :key="index"
                           :src="item.src"
                           :title="item.title"
                           :support-text="item.desc"
            >
            </mdc-grid-tile>
          </mdc-grid-list>
        </mdc-layout-cell>

      </mdc-layout-grid>
    </section>

    <section>
      <mdc-layout-grid>
        <mdc-layout-cell desktop=12>
          <h1>Latest Projects</h1>
        </mdc-layout-cell>

        <mdc-layout-cell desktop="12">
          <mdc-grid-list with-support-text interactive>
            <mdc-grid-tile ratio="16x9"
                           v-for="(item, index) in latestProjects" :key="index"
                           :src="item.src"
                           :title="item.title"
                           :support-text="item.desc"
            >
            </mdc-grid-tile>
          </mdc-grid-list>
        </mdc-layout-cell>
        <mdc-layout-cell desktop=12>
          <mdc-button @click="$router.push('/work')" raised>View Work</mdc-button>
        </mdc-layout-cell>
      </mdc-layout-grid>
    </section>

  </div>
</template>

<script>
  export default {
    name: 'Home',
    data: function () {
      return {
        currentRole: 'Frontend Developer',
        process: [
          {
            src: 'image1.jpg',
            title: 'Research',
            desc: 'lore ipsum'
          },
          {
            src: 'image2.jpg',
            title: 'Wire frames / Mockup\'s',
            desc: 'lore ipsum'
          },
          {
            src: 'image2.jpg',
            title: 'Testing',
            desc: 'lore ipsum'
          },
          {
            src: 'image2.jpg',
            title: 'Technical Architecture',
            desc: 'lore ipsum'
          },
          {
            src: 'image2.jpg',
            title: 'Build',
            desc: 'lore ipsum'
          },
          {
            src: 'image2.jpg',
            title: 'Refine & Review',
            desc: 'lore ipsum'
          }
        ],
        latestProjects: [
          {
            src: 'image1.jpg',
            title: 'Street Salad',
            desc: 'lore ipsum'
          },
          {
            src: 'image2.jpg',
            title: 'Estify Pro',
            desc: 'lore ipsum'
          },
          {
            src: 'image2.jpg',
            title: 'Digital Black Hippy',
            desc: 'lore ipsum'
          }
        ]
      }
    },
    methods: {
      activateUniverseState: function () {
        // let $heroSection = this.$refs.hero
        let $body = document.body
        // let $navBar = document.getElementsByClassName('mdc-top-app-bar')
        $body.classList.add('testing')
        // $navBar.classList.add('mdc-top-app-bar--loading')
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
  h1 {
    /*background: #fff;*/
  }
  .fvs--intro-box h2 {
    /*background: #fff;*/
    line-height: 1.5;
  }
</style>
