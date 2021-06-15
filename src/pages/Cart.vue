<template>
    <div>
        <h1 class="text-3xl">Your Cart</h1>

        <CartItemCard
            v-for="product in products"
            :key="product.id"
            :product="product"
        />
    </div>
</template>

<script>
import CartItemCard from '../components/cart/CartItemCard.vue'
export default {
    name: 'Cart',
    components: {
        CartItemCard,
    },
    computed: {
        products() {
            return this.$store.getters.cartItems
        },
    },
}
</script>

<style></style>
