<template>

    <div>
        <h1>Error Encontrado</h1>
        <h3>{{ error.statusCode }} - {{ error.statusMessage }}</h3>

        <button @click="handleError">Clean Errors</button>
    </div>

</template>



<script setup>
// DEFINIMOS EL COMPORTAMIENTO DEL ERROR. Si accedemos a una ruta
// no permitida desde una url válida, al pulsar el botón nos devolverá
// a esa última ruta válida. Si la ruta desde la que accedemos no está 
// disponible, al pulsar el botón nos redirigirá a la raiz

// Si accedemos escribiendo la url en el navegador, nos devuelve a la raiz
// Si accedemos mediante enlaces válidos con los botones de la web, nos devuelve a esa última ruta válida

    const route = useRoute()

    const { error } = defineProps({
        error: Object
    })

    const path = route.path === error.url ? "/" : route.path

    console.log(route)

    const handleError = () => {
        clearError({ redirect: path })
    }

</script>

<style scoped>
div {
    text-align: center;
}
</style>

