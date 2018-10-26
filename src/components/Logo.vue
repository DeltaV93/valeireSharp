<template>
      <svg width="58px" height="67px" viewBox="0 0 58 67" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
        <g id="Page-1" stroke="none" stroke-width="1" fill="none" fill-rule="evenodd">
          <g id="Apple-Watch-38mm" transform="translate(-95.000000, -174.000000)">
            <g id="Group-2" transform="translate(98.000000, 177.000000)">
              <path d="M13,44.3342318 L39.8736559,44.3342318" id="eart--bottom" v-bind:stroke=[outlineColor] stroke-width="2" stroke-linecap="square" transform="translate(26.541667, 44.607143) scale(1, -1) translate(-26.541667, -44.607143) "></path>
              <path d="M25.5,24.3571429 L6.5,56.3571429" id="v--left" v-bind:stroke=[primaryColor] stroke-width="6" stroke-linecap="square" transform="translate(16.333333, 40.428571) scale(1, -1) translate(-16.333333, -40.428571) "></path>
              <path d="M44.8333333,24.3571429 L26.8333333,55.3571429" id="v--right" v-bind:stroke=[primaryColor] stroke-width="6" stroke-linecap="square" transform="translate(36.166667, 39.928571) scale(-1, -1) translate(-36.166667, -39.928571) "></path>
              <path d="M47.6666667,22.5896246 L4.51405729,22.5896246" id="eart--top" v-bind:stroke=[outlineColor] stroke-width="4" stroke-linecap="square" transform="translate(26.000000, 22.385135) scale(-1, -1) translate(-26.000000, -22.385135) "></path>
              <ellipse id="taurus--circle" v-bind:stroke=[outlineColor] stroke-width="6" cx="26" cy="34.7142857" rx="26" ry="25.7142857"></ellipse>
              <path d="M6,0 C14.7941176,4.01470588 21.3897059,6.02205882 25.7867647,6.02205882 C30.1838235,6.02205882 36.5882353,4.01470588 45,0" id="taurus--horns" v-bind:stroke=[outlineColor] stroke-width="5" stroke-linecap="square"></path>
            </g>
          </g>
        </g>
      </svg>
</template>

<script>
  export default {
    name: 'Logo',
    data () {
      return {
        outlineColor: '#020100',
        primaryColor: '#F7B538'
        // outlineColor: '#fff',
        // primaryColor: '#ffffff'
      }
    }
  }
</script>

<style scoped>

</style>
