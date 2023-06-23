# Vue 3 + Vite


App.vue ---> componente principal

main --> montamos nuestro componente principal correspondiente con un id de un div

index.html --> inyecta nuestra aplicacion 


# API styles

Los componetes de vue se pueden escribir en 2 apis diferentes:
 Options API (Desde vue 2)

 -> Con option api se define la logica d eun componente utilizando un sintaxis de objeto.
 
 
 Composition API (Desde vue 2.7 y recomentada para proyectos de vue3)

 -> Con composition api se definen los componentes utilizando imports tanto para funciones de vue como librerias.
 -> Se añade un setup al scrip
 -> Con composition tiene 2 funciones para reactividad: reactive y ref
 -> Hay ciertas similitudes con react


 # ¿Cual utilizar de los dos?

 -> Composition Api permite tener el codigo mas re-utilizable. Es mas recomendable para proyectos nuevos.
 
 -> Option es recomentado si tu proyecto utiliza pequeñas piezas de vue  y tambien si prefieres el estilo orientado a objetos.

 -> La Option API es el enfoque tradicional y más común en Vue.js, mientras que la Composition API es más flexible y modular, especialmente para proyectos más grandes y complejos.

 -> La Option API es el enfoque clásico de Vue.js y se basa en definir un objeto con opciones en el componente. Es más fácil de entender para principiantes y es adecuado para componentes simples.

-> La Composition API, introducida en Vue 3, es un enfoque más flexible que utiliza funciones reutilizables llamadas composiciones. Permite organizar mejor la lógica del componente, reutilizar código y manejar componentes más grandes y complejos. También proporciona un mejor soporte para el tipado y las herramientas de desarrollo.

-> En resumen, la Option API es más simple y adecuada para proyectos más pequeños, mientras que la Composition API es más poderosa y modular, especialmente para proyectos más grandes y complejos.

# State 

El state o estado Determina la situacion actual denuestra aplicacion
Ejemplo: Si un carrito de compras esta lleno o vacio. Si un cliente acpeto n viaje o no. si un usuario esta autenticado o no.

El state o estado no es siempre es igual. Cambia en base a las interacciones del usuario ( click, formularios, navegar en diferentes paginas)

Ya que tiende a cambiar, utilizaremos las funciones "ref" y "reactive" para declararlo e indenticarlo.

Entonces cada vez que el state cambie el DOM de tu aplicacion se actualizara

# State con reactive

reactive es Siempre un objeto.

import { reactive } from 'vue';

const libro = reactive({
    disponible: true,
    nombre:'moreas',
    precio:-330,
    ISBN:'0-233-32323-323'

})

> para acceder las propiedades.

import { reactive } from 'vue';

console.log(libro.disponible)
console.log(libro.nombre)
console.log(libro.precio)
console.log(libro.ISBN)

> Modificar un reactive

libro.disponible = false;

# State con Ref

> Cuando declaras ReF deberás colocar su valor inicial.

const clientes = ref([]);//Como un array
const libro = ref({})//Como un objeto
const auth = ref(false)//boleano
const sms = ref('Hola')//string

> Para acceder a sus valores

console.log(clientes.value)
console.log(auth.value)
console.log(sms.value)

> Para modificar un ref

clientes.value.push(nuevoCLiente);
auth.value = true;
mensaje.value = 'Adios'


# Para evaluar diferentes valores se recomienda utilizar computed property








