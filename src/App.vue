<template>
<div class="cards-app-container">
    <div class="cards-list-container">
      <h1 class="heading">Learn 4.0 Technologies</h1>
      <p class="description">
        Get trained by alumni of IITs and top companies like Amazon, Microsoft,
        Intel, Nvidia, Qualcomm, etc. Learn directly from professionals involved
        in Product Development.
      </p>
      <div class="cards-list">
        <div v-for="each in cardsList" :key="each.id">
          <CardItem :cardDetails="each" />
          </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';
import CardItem from './components/CardItem.vue';
type data={
  id:number,
  title:string,
  description:string,
  imgUrl:string,
  className:string
}
export default defineComponent({
  name: 'App',
  components: {
    CardItem
  },
  setup(){
    const cardsList:data[] = [
  {
    id: 1,
    title: 'Data Scientist',
    description:
      'Data scientists gather and analyze large sets of structured and unstructured data',
    imgUrl: 'https://assets.ccbp.in/frontend/react-js/data-scientist-img.png',
    className: 'card-1',
  },
  {
    id: 2,
    title: 'IOT Developer',
    description:
      'IoT Developers are professionals who can develop, manage, and monitor IoT devices.',
    imgUrl: 'https://assets.ccbp.in/frontend/react-js/iot-developer-img.png',
    className: 'card-2',
  },
  {
    id: 3,
    title: 'VR Developer',
    description:
      'A VR developer creates completely new digital environments that people can see.',
    imgUrl: 'https://assets.ccbp.in/frontend/react-js/vr-developer-img.png',
    className: 'card-3',
  },
  {
    id: 4,
    title: 'ML Engineer',
    description:
      'Machine learning engineers feed data into models defined by data scientists.',
    imgUrl: 'https://assets.ccbp.in/frontend/react-js/ml-engineer-img.png',
    className: 'card-4',
  },
]


  return {cardsList}
  }
});
</script>

<style scoped>
* {
  box-sizing: border-box;
}
body {
  margin: 0;
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Roboto', 'Oxygen',
    'Ubuntu', 'Cantarell', 'Fira Sans', 'Droid Sans', 'Helvetica Neue',
    sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

.cards-app-container {
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: #f4faff;
  min-height: 100vh;
}

.cards-list-container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 80%;
}

.heading {
  text-align: center;
  color: #171f46;
  font-family: 'Roboto';
  font-size: 48px;
  font-weight: bold;
}

.description {
  text-align: center;
  color: #64748b;
  font-family: 'Roboto';
  font-size: 18px;
  margin-top: 24px;
  max-width: 625px;
}

.cards-list {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  flex-wrap: wrap;
  margin-top: 32px;
  max-width: 1100px;
  padding-left: 0px;
}

@media screen and (min-width: 768px) {
  .cards-list {
    flex-direction: row;
  }
}
</style>