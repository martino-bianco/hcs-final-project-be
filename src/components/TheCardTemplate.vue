<template>
  <router-link :to="'/post/' + travelData.id" id="TheCard" class="tilted">
    <div class="image-container">
      <img
        id="topImage"
        :src="travelData.image"
        alt="Card Image"
        style="width: 100%; height: auto"
      />
    </div>
    <div class="card-details">
      <h1>{{ travelData.city }}</h1>
      <h2>{{ travelData.date }}</h2>
      <div id="author">
        <img id="headShot" :src="travelData.authorpic" alt="" />
        <p id="authorName">{{ travelData.author }}</p>
      </div>
    </div>
  </router-link>
</template>

<script>
import { RouterLink } from 'vue-router'

export default {
  props: {
    travelData: {
      type: Object,
      default: {}
    }
  },
  components: { RouterLink }
}
</script>

<style scoped>
#TheCard {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  width: 200px;
  padding: 20px;
  margin: 40px;
  border-radius: 10px;
  box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.2);
  transition:
    transform 0.6s,
    filter 3s;
}

/* #TheCard.tilted {
  transform: scale(0.9) rotate(-90deg);
} */

#TheCard:hover {
  transform: none; /* Remove the tilt effect on hover */
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
}

.image-container {
  margin-bottom: 10px;
}

.card-details {
  text-align: center;
  display: flex;
  flex-direction: column;
  align-items: center;
}

h1 {
  margin: 0;
  font-size: 24px;
}

h2 {
  margin: 5px 0;
  font-size: 18px;
}

#author {
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: 100%;
  max-width: 100%;
}

#authorName {
  margin: 10px;
  font-size: 16px;
  flex: 1;
  text-align: right;
}

#headShot {
  width: 45px;
  height: 45px;
  border-radius: 50%;
  text-align: left;
  filter: grayscale(100%);
}
</style>
