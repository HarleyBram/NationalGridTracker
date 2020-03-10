<template lang="html">
  <div v-if="region">
    <h2>{{region.shortname}}</h2>
    <p>Intensity Forecast: {{region.intensity.forecast}}</p>
    <ul v-for="(object, index) in region.generationmix[0]" :object='object' :key='index'>
      <li>{{object.fuel}}:{{object.perc}}</li>
    </ul>

  </div>

</template>

<script>
import {eventBus} from '../main.js';

export default {
  name: 'region-detail',
  props: ['region'],
  mounted() {
    eventBus.$on('region-selected', (region) => this.region = region)

  }
}
</script>

<style lang="css" scoped>
</style>
