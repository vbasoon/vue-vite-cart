<template>
    <div class="home">
        <ProductModal :product="product" :active="active.product_modal" />

        <div class="container">
            <h1 class="text-3xl">This is a Home page</h1>
            <div class="flex flex-wrap justify-center product-cards">
                <ProductCardSummary
                    v-for="product in items"
                    :key="product.id"
                    :product="product"
                    v-on:view-product="viewProduct($event)"
                />
            </div>
        </div>
    </div>
</template>

<script>
import items from '../data/items.js'
import ProductCardSummary from '../components/products/ProductCardSummary.vue'
import ProductModal from '../components/products/ProductModal.vue'

export default {
    name: 'Home',
    components: {
        ProductCardSummary,
        ProductModal,
    },
    data() {
        return {
            items,
            product: null,
            active: {
                product_modal: false,
            },
        }
    },
    methods: {
        viewProduct(product) {
            this.product = product
            console.log(this.product)
        },
    },
}
</script>

<style></style>
