<template>
  <div id="position: relative;">
    <maps :highlights="highlights"></maps>
    <today-highlights :highlights="highlights"></today-highlights>
  </div>
</template>

<script>
import Maps from './Maps.vue'
import Highlights from './Highlights.vue'

export default {
  props: ["highlights", 'maps'],
  components: {
    'maps': Maps,
    'today-highlights': Highlights
  },
  data () {
    return {
    
      //tempVar: this.weather_data.temperature,
        //highlights: this.weather_data.highlights,
    }
  },
  methods: {

  },
  computed: {

  },
}
</script>

<style>
#pagecontent{
    border: 1px solid red;
    padding:2px
}
</style>
