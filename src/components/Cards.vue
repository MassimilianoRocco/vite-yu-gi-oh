<script>
    export default {
      name: "Cards",
      props: "singleCard",

  data() {
    return {
      
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
        <div class="card">
            <img :src="singleCard.ygoprodeck_url">
            <p>Nome</p>
            <p>Tipo</p>
        </div>
</template>

<style scoped>
    .card{
        width: calc(100% / 5 - 1rem);
    }
</style>