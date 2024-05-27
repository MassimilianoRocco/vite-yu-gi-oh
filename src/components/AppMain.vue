<script>
import store from '../data/store.js';
import Cards from './Cards.vue';

    export default {
        components: {
        Cards
    },

  data() {
    return {
      store
    }
  },
  methods: {

  },
  created() {
   
  },
  mounted() {

  }
}

</script>

<template>
    <div class="main_container relative">
        <div class="cards_container">
            <div class="found_container">
                <p>Found X cards</p>
            </div>
            <div class="card_box">
                <Cards v-for="card, index in store.cards"  :singleCard="card" :singleCardIndex="index"/>
            </div>
        </div>
    </div>
</template>

<style scoped>
    .main_container{
        background-color: slategrey;
        display: flex;
        justify-content: center;
        align-items: center;
    }
    .cards_container{
        width: 90%;
        background-color: white;
        margin: 5rem 0;
        padding: 2rem 0;
    }
    .found_container{
        width: 80%;
        background-color: darkslategray;
        margin: auto;
    }
    .card_box{
        width: 80%;
        background-color: white;
        margin: auto;
        display: flex;
        flex-wrap: wrap;
        gap: 1rem;
        text-align: center;
    }
    
</style>
