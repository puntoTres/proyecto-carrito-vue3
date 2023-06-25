  
<script setup>
/* Código JavaScript */
import { ref,reactive,onMounted } from 'vue';
import { db } from './data/guitarras';
import Guitarra from './components/Guitarras.vue';
import Header from './components/Header.vue';
import Footer from './components/Footer.vue'


//Recoger bbdd desde una variable State ref
// const guitarras = ref(db);
// console.log(guitarras.value)

//Recoger bbdd desde una variable State reactive
// const state = reactive({
//     guitarras: db
// })
// console.log(state.guitarras)

//


//En un ejemplo real de vue se utilizaras metodos del ciclo de vida de vue, sus fases
const guitarras = ref([]);// State ref
const carrito = ref([]);
//const numero = ref(0) declaro e inicializo la variable
// const state = reactive({
//     guitarras: []
// });// State ref

//Callback
onMounted(()=>{//Ejecuta todo lo que hay dentro cuando el componente se ha sido montado en el dom
    guitarras.value = db;
    // state.guitarras = db;
})


const agregarCarrito = (guitarra) =>{
    // numero.value++;
    guitarra.cantidad = 1;
    console.log('Agregando...',guitarra)
    carrito.value.push(guitarra);
}


</script>

<template>
    <Header :carrito="carrito"/>
    <main class="container-xl mt-5">
        <h2 class="text-center">Nuestra Colección</h2>
        <div class="row mt-5">
            <Guitarra v-for="guitarra in guitarras"  
            :guitarra="guitarra"
             @agregar-carrito="agregarCarrito"/><!-- Renderiza el componente -->
        </div>
    </main>
    <Footer/>
</template>

 