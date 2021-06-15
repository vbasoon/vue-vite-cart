<template>
    <div class="cards container w-100 mx-auto">
        <h1 class="text-3xl">Your Cart</h1>

        <CartItemCard
            v-for="product in products"
            :key="product.id"
            :product="product"
        />

        <CartSummaryPaymentCard :products="products" />
    </div>
</template>

<script>
import CartItemCard from '../components/cart/CartItemCard.vue'
import CartSummaryPaymentCard from '../components/cart/CartSummaryPaymentCard.vue'
export default {
    name: 'Cart',
    components: {
        CartItemCard,
        CartSummaryPaymentCard,
    },
    computed: {
        products() {
            return this.$store.getters.cartItems
        },
    },
}
</script>

<style></style>
