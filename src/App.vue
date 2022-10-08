<template>
  <div class="container align-self-center">
    <CardVue v-if="!submitStatus" @submitted="updateRating" />
    <ThankVue :rating="my_rating" v-if="submitStatus"/>
    <div class="attribution text-center mt-5" style="width: 22rem;">
      Challenge by <a
        href="https://www.frontendmentor.io/challenges/interactive-rating-component-koxpeBUmI/hub/interactive-rating-component-1U6dRSZ5Wp"
        target="_blank">Frontend Mentor</a>.
      Coded by <a href="https://www.linkedin.com/in/salahudheen-k-7574ba1a6/">Salahudheen</a>.
    </div>
  </div>
</template>

<script>
import CardVue from './components/Card.vue';
import ThankVue from './components/Thank.vue'
export default {
  name: 'App',
  components: {
    CardVue,
    ThankVue,
  },
data(){
  return{
    my_rating:0,
    submitStatus:false
  }
},
methods:{
  updateRating(e){
    this.my_rating=e
    this.submitStatus=true
  }
}
}
</script>

<style scoped>
.container {
  width: fit-content;
  margin-top: 25vh;
}

.text-center {
  color: var(--Light-pGrey);
}
</style>