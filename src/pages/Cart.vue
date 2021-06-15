<template>
    <div>
        <h1 class="text-3xl">Your Cart</h1>

        <div v-for="product in items" :key="product.id">
            {{ product.name }}
        </div>
    </div>
</template>

<script>
import CartItemCard from '../components/products/CardItemCard.vue'
export default {
    name: 'Cart',
    components: {
        CartItemCard,
    },
    computed: {
        items() {
            return this.$store.getters.cartItems
        },
    },
}
</script>

<style></style>
