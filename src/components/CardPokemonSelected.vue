<script setup>
import 'animate.css';
const pokemon = defineProps(["name", "xp", "height" , "img", "loading"])
</script>

<template>
    <div class="card CardPokemonSelected"
    :class="loading ? '' : 'animate__animated animate__flipInY'">
        <img 
        v-if="pokemon.name"
        :src="pokemon.img"
        height="250" 
        class="card-img-top pt-2" 
        :alt="pokemon.name"
        >
        <img 
        v-else
        src="../assets/pokeball.jpg"
        height="250" 
        class="card-img-top pt-2" 
        alt="???"
        >
        <div 
        v-if="pokemon.name"
        class="card-body">
            <h5 class="card-title">{{ pokemon.name }}</h5>
            <hr>

            <div class="row">
                <section class="col">
                    <strong>XP: </strong>
                    <span>{{ pokemon.xp }}</span>
                </section>
                <section class="col">
                    <strong>Altura: </strong>
                    <span>{{ pokemon.height }}</span>
                </section>
            </div>
        </div>
        <div 
        v-else
        class="card-body">
           
            <hr>

            <div class="row">
                <section class="col">
                    <strong>Pesquise seu Pokemon, clique e descubra!!! </strong>
                </section>
            </div>
        </div>
    </div>

</template>

<style scoped>
    .CardPokemonSelected {
        height: 75vh;
        background: rgb(72,63,251);
        background: radial-gradient(circle, rgba(72,63,251,0.8071613641456583) 0%, rgba(70,252,244,0.5102415966386555) 100%); 
    }
</style>