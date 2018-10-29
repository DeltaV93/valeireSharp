<template>
  <div id="fvs--home" ref="hero">
    <section class="fvs--intro-box">
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
        <mdc-layout-cell desktop=7 tablet=12 >
          <div>
            <mdc-text
              typo="headline1"
              tag="h1"
              class="text-left">Valerie Sharp</mdc-text>
            <mdc-text
              typo="headline5"
              tag="h2"
              class="text-left">I jump between the <span id="ux-universe" v-on:mouseover="activateUniverseState">UX Universe</span> to <span id="coding-cosmos" v-on:mouseover="activateCosmosState">Coding Consolations</span> to create user centered digital experiences</mdc-text>
            <mdc-layout-cell desktop=7 tablet=12 class="fvs--intro-box--action">
              <mdc-button @click="$router.push('/work')" raised>View Work</mdc-button>
              <mdc-button @click="Contact" outlined>Contact Me</mdc-button>
            </mdc-layout-cell>
          </div>
          <script type="in/Login"></script>
        </mdc-layout-cell>
      </mdc-layout-grid>
    </section>
    <section class="fvs--my-process" ref="my-process">
      <mdc-layout-grid>
        <mdc-layout-cell desktop=12 tablet=12>
          <h1 class="text-center">My Process</h1>
          <h2>From gathering business requirements to pushing to productions</h2>
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

    <section class="fvs--my-tool-box" ref="my-tool-box">
      <mdc-layout-grid>
        <mdc-layout-cell desktop=12 tablet=12>
          <h1 class="text-center">My Tool Box</h1>
        </mdc-layout-cell>

        <mdc-layout-cell desktop=12>
          <mdc-grid-list with-support-text interactive>
            <mdc-grid-tile ratio="16x9"
                           v-for="(item, index) in toolBox" :key="index"
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
        ],
        toolBox: [
          {
            src: 'image1.jpg',
            title: 'Development',
            desc: 'lore ipsum',
            skills: {
              'Front End': ['HTML/CSS', 'Sass', 'JavaScript/jQuery', 'Bootstrap', 'Vue', 'React'],
              'Back End': ['PHP', 'Python', 'Java', 'SQL']
            }
          },
          {
            src: 'image2.jpg',
            title: 'User Experiences',
            desc: 'lore ipsum',
            skills: {
              'Research': ['surveys', 'interviews', 'persona', 'usability', 'testing'],
              'Design': ['Sketch', 'Adobe XD', 'Figma', 'InVision', 'Wire Framing', 'Rapid Prototyping']
            }
          },
          {
            src: 'image2.jpg',
            title: 'Soft Skills',
            desc: 'lore ipsum',
            skills: ['Communication', 'Public Speaking', 'Teaching', 'Mentoring']
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
    max-width: 80%;
    height: auto;
    max-height: 850px;
    left: -8vw;
    top: 10%;
    position: relative;
  }
  .fvs--personal-img img{
    /*height: 358.391px;*/
    /*width: 418.109px;*/
  }
  .fvs--personal-img:before {
    content: "\00a0 ";
    position: absolute;
    /*min-height: 28%;*/
    min-height: 55%;
    min-width: 30%;
    max-height: 95%;
    max-width: 30%;
    /*height: 38rem;*/
    /*width: 25rem;*/
    width: 25rem;
    display: block;
    top: 124px;
    animation: float 9s ease-in-out infinite;
    /*background-color: #246464;*/
    border: 5px solid #020100;
    z-index: -3;
  }
  h1 {
    /*background: #fff;*/
  }
  .fvs--intro-box h1 {
    margin-bottom: 0;
  }
  .fvs--intro-box h2 {
    /*background: #fff;*/
    line-height: 1.5;
  }


  /* TABLETBREAKPOINT */
  @media only screen and (max-width: 959px){
    .fvs--personal-img:before {
      min-height: 51.5%;
    }
  }
  /* MOBILE BREAKPOINT */
  @media only screen and (max-width: 600px){
    .fvs--personal-img:before {
      min-height: 25%;
    }
  }
</style>
