<template>
<div class="container">
    <h1 class="text-center">Ürün Ekleme Uygulaması</h1>
    <hr>
    <appNewProduct></appNewProduct>
    <appProgress></appProgress>
   
    <appProducts></appProducts>
    

</div>
</template>

<script>
import NewProduct from '../src/components/NewProduct.vue';
import Progress from '../src/components/Progress.vue';
import Products from '../src/components/Products.vue'

export default {
    components: {
    appNewProduct: NewProduct,
    appProgress: Progress,
    appProducts:Products
}
}
</script>

<style>
body {
    background-color: aliceblue;
    padding-top: 20px;
    padding-bottom: 20px;
}


</style>
