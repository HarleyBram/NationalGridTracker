<template lang="html">
<div>
  <h3>Select a region:</h3>
  <ul>
    <region-item v-for="(region, index) in regionListArray.data[0].regions" :region='region' :key="index"/>
  </ul>

</div>
</template>

<script>
import RegionItem from './RegionItem.vue'
export default {
  name: 'region-list',
  props: ["regionListArray"],
  components: {
    'region-item': RegionItem
  }
}
</script>

<style lang="css" scoped>
</style>
