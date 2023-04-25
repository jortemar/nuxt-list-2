<template>
<Head>
    <Title>Post {{ id }}</Title>
</Head>

    <h2>Bienvenido al Post #{{ id }}</h2>
</template>

<script setup>
//  const route = useRoute().params;
    const { id } = useRoute().params

    

    definePageMeta({
        validate: async (route) => {
            const nuxtApp = useNuxtApp()

            // console.log(route)
            // console.log(nuxtApp)

            if (!/^[0-9]+$/.test(route.params.id)) {
                throw createError ({
                    statusCode: "500",
                    statusMessage: "Param Type Is Invalid"
                })
            }

            return true
        }
    })
   
   
</script>