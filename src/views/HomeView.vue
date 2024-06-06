<script setup>
import { onMounted, reactive, ref } from "vue";
import ListPokemons from "../components/ListPokemons.vue";
let urlBaseSvg = ref("https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/")
let pokemons = reactive(ref());

onMounted (()=>{
  fetch("https://pokeapi.co/api/v2/pokemon?limit=151&offset=0")
  .then(res => res.json())
  .then(res => pokemons.value = res.results);
  
})

</script>

<template>
  <main>
    <div class="container text-center">
  <div class="row mt-5">
    <div class="col-sm-12 col-md-6">
      <div class="card">
        <img src="https://claudia.abril.com.br/wp-content/uploads/2020/01/filtro-pikachu-snapchat-1.jpg?quality=85&strip=info&w=1280&h=720&crop=1" class="card-img-top" alt="...">
        <div class="card-body">
          <h5 class="card-title">Card title</h5>
          <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
        </div>
      </div>
    </div>
    <div class="col-sm-12 col-md-6">
      <div class="card">
        <div class="card-body row">
          <ListPokemons 
          v-for="pokemon in pokemons"
          :key="pokemon.name"
          :name="pokemon.name"
          :urlBaseSvg="urlBaseSvg + pokemon.url.split('/')[6] + '.svg'" 
          />
        </div>
      </div>
    </div>
  </div>
</div>
  </main>
</template>
