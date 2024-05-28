<script>
import store from '../data/store.js';
import Cards from './Cards.vue';

    export default {
        components: {
        Cards
    },

  data() {
    return {
      store,
      archetype: "",
    }
  },
  methods: {

  },
  computed: {
    // archTypeList(){
    //         if(this.archetype){
                
    //             return this.store.cards.filter((card)=>card.archetype.includes(this.archetype));
    //         }
    //         return this.store.cards;
    //     }
  },
  created() {
   
  },
  mounted() {
  }
}

</script>


<!-- TEMPLATE -->
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
        <div class="absolute_selection_box">
            <label for="cars">Choose an archetype</label><br>
            <select v-model="archetype" name="cars" id="cars">
                <option v-for="arch in store.archetypeList" value="archSelection">{{ arch.archetype_name }}</option>
            </select>
        </div>
    </div>
</template>


<!-- STYLE -->
<style scoped>
    .relative{
        position: relative
    }
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
        color: white;
        font-size: 1.2rem;
        padding: 0.5rem;
    }
    .card_box{
        width: 80%;
        background-color: white;
        margin: auto;
        display: flex;
        justify-content: space-between;
        flex-wrap: wrap;
        gap: 1rem;
        text-align: center;
    }

    .absolute_selection_box{
        position: absolute;
        top:1%;
        left: 15%;
        color: white;
    }
    
</style>
