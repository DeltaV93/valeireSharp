<template>
  <svg width="226px" height="183px" viewBox="0 0 226 183" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
    <g id="Artboard" stroke="none" stroke-width="1" fill="none" fill-rule="evenodd">
      <g id="valerieSharp--logo" transform="translate(3.000000, 1.000000)">
        <polygon id="triangle" v-bind:stroke=[outlineColor] stroke-width="11.4" transform="translate(110.000000, 83.098901) scale(1, -1) translate(-110.000000, -83.098901) " points="110 5.95604396 209.908257 160.241758 10.0917431 160.241758"></polygon>
        <path d="M185.736321,140.073329 C185.736321,131.27386 182.754395,124.082805 176.790453,118.499949 C170.826511,112.917092 160.440027,107.98133 145.630688,103.692513 C129.615159,99.2558061 117.486426,93.4881735 109.244124,86.3894423 C101.001823,79.2907111 96.8807339,69.7149622 96.8807339,57.6619082 C96.8807339,45.3130737 101.487642,35.2566887 110.701597,27.4924515 C119.915552,19.7282142 131.759495,15.8461538 146.23378,15.8461538 C156.285368,15.8461538 168.447727,20.4677005 182.72086,29.7107939 L176.790453,38.6507368 C164.326587,30.9900457 154.141029,27.1597001 146.23378,27.1597001 C134.506929,27.1597001 125.343369,30.0435164 118.742827,35.8112355 C112.142285,41.5789546 108.842063,48.7515233 108.842063,57.3291568 C108.842063,65.4631196 111.890999,72.2474823 117.988962,77.6824484 C124.086925,83.1174145 134.607428,87.9052889 149.550788,92.0462155 C165.298274,96.4829225 177.276236,102.472387 185.485032,110.014789 C193.693829,117.557191 197.798165,127.50266 197.798165,139.851494 C197.798165,152.717945 193.023733,162.95919 183.474725,170.575537 C173.925717,178.191884 161.746727,182 146.937388,182 C141.400223,182 130.837496,179.369131 115.249207,174.107393 L121.013345,163.656131 C133.756939,168.416958 142.398286,170.797371 146.937388,170.797371 C158.530219,170.797371 167.894807,167.987499 175.031434,162.36767 C182.168061,156.747841 185.736321,149.316468 185.736321,140.073329 Z" id="s--outline" v-bind:fill=[outlineColor]></path>
        <polygon id="v--outline__right" v-bind:fill=[primaryColor] points="109.98952 170.724418 220.372939 0.195620474 206.902238 0.195620474 109.98952 149.607236"></polygon>
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
        primaryColor: '#BDE6BE'
        // primaryColor: '#F7B538'
      }
    },
    methods: {
      darkTheme (primaryColor) {
        this.outlineColor = 'white'
        this.primaryColor = primaryColor || this.primaryColor
      },
      lightTheme () {
        this.outlineColor = '#020100'
        // this.primaryColor = primaryColor || this.primaryColor
      },
      changeColors (updateOutlineColor, updatePrimaryColor) {
        this.outlineColor = updateOutlineColor
        this.primaryColor = updatePrimaryColor
      }
    },
    mounted: function () {
      // this.changeColors('lightblue', 'purple')
    }
  }
</script>

<style scoped>

</style>
