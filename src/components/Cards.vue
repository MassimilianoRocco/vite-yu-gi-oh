<script>
    export default {
      name: "Cards",
      props: {
        singleCard: Object,
        singleCardIndex: Number,
      },
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
            <img :src="singleCard.card_images[0].image_url">
            <p>{{singleCard.name ?  singleCard.name : 'No Name'}}</p>
            <p>{{ singleCard.archetype ? singleCard.archetype : "Nessun archetipo"  }}</p>
        </div>
</template>

<style scoped>
    .card{
        width: calc(100% / 5 - 1rem);
        background-color: slategrey;
        color: white;
    }
    .card img{
      width: 100%;
      object-fit: cover;
    }
</style>