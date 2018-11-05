<template>
  <div id="fvs--home" ref="hero">
    <section class="fvs--intro-box">
      <mdc-layout-grid>
        <mdc-layout-cell desktop=1 tablet=12 >
          <Stars></Stars>
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
              <mdc-button @click="contactModal" outlined>Contact Me</mdc-button>
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
            <mdc-layout-cell desktop=2 v-for="(item, index) in process" :key="index">
              <div class="process">
                <img :src='"/static/icons/"+item.src'>
                <p>{{item.title}}</p>
                <p>{{item.desc}}</p>
              </div>
            </mdc-layout-cell>
      </mdc-layout-grid>
    </section>

    <section class="fvs--my-tool-box" ref="my-tool-box">
      <mdc-layout-grid>
        <mdc-layout-cell desktop=12 tablet=12>
          <h1 class="text-center">My Tool Box</h1>
        </mdc-layout-cell>
          <mdc-layout-cell desktop=4 v-for="(item, index) in toolBox" :key="index">
            <img :src='"/static/icons/"+item.icon' alt="">
            <p>{{item.title}}</p>
            <ul>
              <li v-for='(skill, key, index) in item.skills' :key='index'>
                <div v-if="item.title === 'Soft Skills'" >{{skill}}</div>
                <div v-else>
                  <div>{{key}}</div>
                  <div v-for="(item, index) in skill" :key="index">

                    <ul>
                      <li>{{item}}</li>
                    </ul>
                  </div>
                </div>
              </li>
            </ul>
          </mdc-layout-cell>
      </mdc-layout-grid>
    </section>

    <section>
      <svg id="div--waves" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink"  viewBox="0 0 1920 222" version="1.1">
        <g id="Page-1" stroke="none" stroke-width="1" fill="none" fill-rule="evenodd">
          <path d="M0,123.11773 C174.342354,174.442004 339.457535,200.104141 495.345541,200.104141 C1011.63072,200.104141 1279.00221,3.41060513e-13 1551.62147,3.41060513e-13 C1706.04155,3.41060513e-13 1828.8344,30.5786532 1920,91.7359595 L1920,221.172026 L0,221.664068 L0,123.11773 Z" id="Rectangle" fill="#ffffff"/>
        </g>
      </svg>
      <div class="projects">
      <mdc-layout-grid>
        <mdc-layout-cell desktop=12>
          <h1>Latest Projects</h1>
          <div class="projects">
            <div class="project--container" v-for="(item, index) in latestProjects" :key="index">
              <mdc-layout-grid :class="">
                <mdc-layout-cell desktop=5>
                  <div class="project__img">
                    <img v-bind:src='"/static/img/"+item.src' class="img--responsive" v-bind:alt=[item.title]>
                  </div>
                </mdc-layout-cell>
                <mdc-layout-cell desktop=1>
                  <div class="project__info">
                    <mdc-text
                      typo="headline4"
                      tag="h4"
                      class="text-left project__info--title">{{item.title}}</mdc-text>
                    <mdc-text
                      typo="headline6"
                      tag="p"
                      class="text-left">{{item.desc}}</mdc-text>
                  </div>
                </mdc-layout-cell>
              </mdc-layout-grid>
            </div>
          </div>
        </mdc-layout-cell>
        <mdc-layout-cell desktop=12>
          <mdc-button @click="$router.push('/work')" raised>View Work</mdc-button>
        </mdc-layout-cell>
      </mdc-layout-grid>
      </div>
    </section>

  </div>
</template>

<script>
  import Stars from '@/components/Stars'

  export default {
    name: 'Home',
    props: ['contactDialog'],
    data: function () {
      return {
        contactMe: false,
        currentRole: 'Frontend Developer',
        process: [
          {
            src: 'Search.svg',
            title: 'Research',
            desc: 'Observe the current flows and through user testing & market research find the best strategy to reach business goals.'
          },
          {
            src: 'Structure.svg',
            title: 'Wire frames / Mockup\'s',
            desc: 'Create low fidelity prototypes as a way to create feedback loop'
          },
          {
            src: 'UXDevelopment.svg',
            title: 'Testing',
            desc: 'Using the prototypes I\'m able to test assumptions that allow me to iterate on user flows quickly'
          },
          {
            src: 'programmingSolutions.svg',
            title: 'Technical Architecture',
            desc: 'Whether I\'m building from the ground up or adding functionality I determine the best architecture for the project and selecting which standards to follow during development.'
          },
          {
            src: 'build.svg',
            title: 'Build',
            desc: 'Using the framework decided in the precarious step I start implementing the design, while staying flexible to any architectural changes I may need to make due to unforeseen elements.'
          },
          {
            src: 'updates.svg',
            title: 'Refine & Review',
            desc: 'Continue to update and improve based on user feedback, web optimizing, and analytics.'
          }
        ],
        latestProjects: [
          {
            src: 'street-salad-logo.png',
            title: 'Street Salad',
            desc: 'lore ipsum'
          },
          {
            src: 'estify-logo.png',
            title: 'Estify Pro',
            desc: 'lore ipsum'
          },
          {
            src: 'https://via.placeholder.com/100x50',
            title: 'Digital Black Hippy',
            desc: 'lore ipsum'
          }
        ],
        toolBox: [
          {
            src: 'https://via.placeholder.com/100x100',
            title: 'User Experiences',
            icon: 'tools.svg',
            skills: {
              'Research': ['surveys', 'interviews', 'persona', 'usability', 'testing'],
              'Design': ['Sketch', 'Adobe XD', 'Figma', 'InVision', 'Wire Framing', 'Rapid Prototyping']
            }
          },
          {
            src: 'https://via.placeholder.com/100x100',
            title: 'Development',
            icon: 'programCoding.svg',
            skills: {
              'Front End': ['HTML/CSS', 'Sass', 'JavaScript/jQuery', 'Bootstrap', 'Vue', 'React'],
              'Back End': ['PHP', 'Python', 'Java', 'SQL']
            }
          },
          {
            src: 'https://via.placeholder.com/100x100',
            title: 'Soft Skills',
            icon: 'VectorIllustration.svg',
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
        $body.classList.add('body--ux-universe')
        // $navBar.classList.add('mdc-top-app-bar--loading')
      },
      activateCosmosState: function () {

      },
      contactModal: function () {
        // console.log()
        // this.contactDialog()
        this.$emit('contactMe')
        // console.log('call me. beep me.')
      }
    },
    components: {
      Stars
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
  .fvs--personal-img img {
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
  .process {
    text-align: center;
  }
  .process img,
  .fvs--my-tool-box img{
    height: 100px;
    width: 100px;
  }
  #div--waves {
    width: 100%;
    height: 100%;
  }
  .projects {
    background: #fff;
    position: relative;
    top: -5px;
    color: black;
    /*transform: skewY(-2deg);*/
  }
  .project--container  img{
    height: auto;
    width: 100%;
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
