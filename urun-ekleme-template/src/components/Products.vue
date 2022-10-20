<template>
<div v-if="!productList.lenght">
      <h3 class="text-center"> Eklenen Ürünlerin Listesi</h3>
      <hr>
    <div class="row product-container">
        <appProduct v-for="product in productList" :key="product.index">
            <img class="card-img-top" :src="product.selectedImage" alt="Card image cap">
            <div class="card-body">
                <h5 class="card-title">{{product.title}}</h5>
                <small>
                    <strong>Adet : </strong> {{product.count}}
                </small>
                <br>
                <small>
                    <strong>Fiyat : </strong> {{product.price}}
                </small>
                <br>
                <small>
                    <strong>Tutar : </strong> {{product.totalPrice}}
                </small>
            </div>
        </appProduct>
    </div>
</div>
</template>

<script>
import Product from './Product.vue';
import {
    eventBus
} from '../main'
export default {
    components: {
        appProduct: Product
    },
    data: function () {
        return {
            productList: [],
        }
    },
    created() {
        eventBus.$on("productAdded", (product) => {
            if (this.productList.length < 2) {
                this.productList.push(product);
                eventBus.$emit("progressBarUpdate", this.productList.length)
            } else {
                alert("Daha fazla ürün ekleyemezsiniz!!!")
            }

        })
    }
}
</script>

<style >
.card {
    margin-right: 5px;
    margin-bottom: 5px;
}

.card:last-child {
    margin-right: 0px;
}

.col-md-2 {
    max-width: 15.666667% !important;
}

.product-container {
    margin-left: 15px;
}
</style>
