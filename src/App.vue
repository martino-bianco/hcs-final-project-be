<template>
  <router-view />
  <div id="cardContainer">
    <TheCardTemplate
      v-for="travelItem in travelsData"
      :key="travelItem.id"
      :travelData="travelItem"
    />
  </div>
</template>

<script>
import travelsData from '../public/travels.json' // Adjust the path as needed

export default {
  data() {
    return {
      travelsData: [] // Initialize an empty array to hold the data
    }
  },
  mounted() {
    this.travelsData = travelsData // Assign the imported JSON data to the component's data property
  }
}
</script>

<style scoped></style>

<!-- <template>
  <router-view />
  <TheMenuBar />
  <div id="container">
    <div id="leftColumn">
      <ThePreviewCards />
    </div>
    <div id="rightColumn">
      <TheMap />
    </div>
  </div>
</template>

<script>
import TheMap from './components/TheMap.vue'
import TheMenuBar from './components/TheMenuBar.vue'
import ThePreviewCards from './components/ThePreviewCards.vue'

export default {
  components: { TheMenuBar, ThePreviewCards, TheMap }
}
</script>

<style scoped>
#container {
  display: flex;
}

#leftColumn {
  flex: 1;
  padding: 16px;
}

#rightColumn {
  flex: 1;
  padding: 16px;
  height: 800px;
}
</style> -->
