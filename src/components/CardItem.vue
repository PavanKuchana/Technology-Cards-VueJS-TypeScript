<template>
    <div class="card-item">
       <div :class = "cardDetails.className">
      <h1 class="card-title">{{cardDetails.title}}</h1>
      <p class="card-description">{{cardDetails.description}}</p>
      <div class="img-container">
        <img class="card-img" :src="cardDetails.imgUrl" :alt="cardDetails.title" />
      </div>
      </div>
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import { PropType } from '@vue/runtime-core'
type data={
  id:number,
  title:string,
  description:string,
  imgUrl:string,
  className:string
}
export default defineComponent({
    name:'CardItem',
    props:{
        cardDetails:{
            type:Object as PropType<data>,
            required:true
        }
    },
})
</script>


<style scoped >
.card-item {
  background-color: #ffffff;
  border-radius: 20px;
  padding-left: 24px;
  padding-right: 24px;
  padding-top: 32px;
  padding-bottom: 32px;
  margin-left: 24px;
  margin-right: 24px;
  margin-bottom: 48px;
  max-width: 323px;
  list-style-type: none;
}

.card-1 {
  border-top: 5px solid #ff4f64;
}

.card-2 {
  border-top: 5px solid #00a8e7;
}

.card-3 {
  border-top: 5px solid #44c4a1;
}

.card-4 {
  border-top: 5px solid #fcc200;
}

.card-title {
  color: #171f46;
  font-family: 'Roboto';
  font-size: 18px;
  font-weight: 500;
}

.card-description {
  color: #64748b;
  font-family: 'Roboto';
  font-size: 14px;
}

.img-container {
  display: flex;
  justify-content: flex-end;
}

.card-img {
  width: 80px;
  height: 80px;
}
</style>