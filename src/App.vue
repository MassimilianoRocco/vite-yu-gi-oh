<script>
import AppHeader from './components/AppHeader.vue'
import AppMain from './components/AppMain.vue'
import store from './data/store.js'

import axios from 'axios';

export default {
  components: {
    AppHeader,
    AppMain,

  },
  data() {
    return {
      store,
      archetype: "",
      count: 0,
    }
  },
  methods: {
    getSearchedListCard(){
      if(this.archetype ==""){
          axios.get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=200&offset=0").then(risultato => {
          this.store.cards = risultato.data.data;
          this.count = this.store.cards.length;
        });
      }
      else{
        axios.get("https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype="+this.archetype).then(risultato => {
          this.store.cards = risultato.data.data;
          this.count = this.store.cards.length;
        });
      }
    }
  },
  created() {
    this.getSearchedListCard();
    axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php').then(resp =>{
        this.store.archetypeList = resp.data;
      });
  },
  mounted() {

  }
}
</script>

<template>
  <AppHeader/>
  <AppMain/>
  <div class="absolute_selection_box">
      <label for="cars">Choose an archetype</label><br>
      <select v-model="archetype" @change="getSearchedListCard()">
          <option v-for="arch in store.archetypeList" :value= "arch.archetype_name">{{ arch.archetype_name }}</option>
      </select>
      <div class="found_container">
          <p>Found {{ this.count }} Cards </p>
      </div>
  </div>
  
</template>

<style scoped>
  .absolute_selection_box{
        position: absolute;
        top: 12%;
        left: 15%;
        color: white;
    }
</style>
