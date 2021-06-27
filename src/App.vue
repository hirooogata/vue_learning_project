<template>
  <div>
    <Header :username='name' v-model="InputData.condition"></Header>
    <Body @add="add1"></Body>
    <Body @add="add2"></Body>
    <Footer :userage='year'></Footer>
    <div class="result">
      <h2 class="result__title">Result</h2>
      <p class="result__total">total : {{ totalcount }} </p>
      <p class="result__condition">condition : {{ InputData.condition }} </p>
    </div>

    <button @click="componentName = 'Header'">Header</button>
    <button @click="componentName = 'Body'">Body</button>
    <keep-alive>
      <component :is="componentName"></component>
    </keep-alive>

  </div>
</template>

<script>
import Header from './components/Header.vue'
import Body from './components/Body.vue'
import Footer from './components/Footer.vue'

export default {
  data(){
    return {
      name: "hirohiro",
      year: "3",
      count1: 0,
      count2: 0,
      totalcount: 0,
      componentName: "Header",
      InputData: {
        condition: ""
      }
    }
  },
  components: {
    Header,
    Body,
    Footer
  },
  methods:{
    add1(count){
      this.count1 = count;
      this.totalcount = this.count1 + this.count2;
    },
    add2(count){
      this.count2 = count;
      this.totalcount = this.count1 + this.count2;
    }
  }
}
</script>

<style scoped lang="scss">
.result {
    border: 1px solid #000;
    padding: 15px;
    margin: 5px 0;

    &__total {
        color: #000;
    }

    &__condition {
        color:#000;
    }
}
</style>