<script setup>
import {ref} from 'vue'; //importo la variable ref desde la libreria de vue
// const numero = ref(0)// declaro e inicializo la variable


//Los props no requiren importarse
const props = defineProps({
    guitarra: {//llamamos al prop con el mismo nombre que el padre
        type: Object,//definimos el tipo de dato
        required: true//Lo ponemos requerido.
    }

});

defineEmits(['agregar-carrito']);
</script>

<template>
  <div class="col-md-6 col-lg-4 my-4 row align-items-center">
                <div class="col-4">
                    <img class="img-fluid" :src="'/public/img/'+guitarra.imagen+'.jpg'" 
                    :alt="'imagen guitarra'+guitarra.nombre">
                </div>
                <div class="col-8">
                    <p>{{ numero }}</p>
                    <h3 class="text-black fs-4 fw-bold text-uppercase">{{ guitarra.nombre }}</h3>
                    <p>{{ guitarra.descripcion }}</p>
                    <p class="fw-black text-primary fs-3">${{ guitarra.precio }}</p>
                    <!--
                        Evento tipo inline 'v-on:click="numero++"'
                        <button 
                        type="button" v-on:click="numero++"
                        class="btn btn-dark w-100 "
                    >Agregar al Carrito</button> -->
                    <button 
                        type="button" @click="$emit('agregar-carrito',guitarra)"
                        class="btn btn-dark w-100 ">Agregar al Carrito</button> 
                </div>
    </div><!-- FIN GUITARRA -->
</template>