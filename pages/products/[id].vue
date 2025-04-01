<template>
 <div>
    <Head>
        <Title>Nuxt ecomm | {{ items.title }}</Title>
        <Meta name="description" :content="items.description"/>
    </Head>
    <ProductDetails :product="items"/>
</div>
</template>

<script setup>
const routes = useRoute()
const id = routes.params.id

const {data:items} = await useFetch(`https://fakestoreapi.com/products/${id}`)

if(!items.value){
    throw createError({statusCode:404, statusMessage: 'lolll product not found',fatal:true})
}
</script>
