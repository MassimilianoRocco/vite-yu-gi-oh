<script>
import AppHeader from './components/AppHeader.vue'
import AppMain from './components/AppMain.vue'
import store from './data/store.js'

export default {
  components: {
    AppHeader,
    AppMain,

  },
  data() {
    return {
      store
    }
  },
  methods: {

  },
  created() {
    axios.get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0").then(risultato => {
      this.store.cards = risultato.data.results;
    });
  },
  mounted() {

  }
}
</script>

<template>
  <AppHeader/>
  <AppMain/>
</template>

<style scoped>

</style>
