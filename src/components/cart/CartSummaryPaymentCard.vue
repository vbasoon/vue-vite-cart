<template>
    <div class="cart-item-card">
        <h3 class="font-bold">Cart Total: ${{ cart_total.toFixed(2) }}</h3>

        <button
            class="
                view-product-button
                border-2
                bg-gray-600
                text-white
                rounded-xl
                p-2
            "
        >
            Pay by Credit Card
        </button>
    </div>
</template>

<script>
export default {
    name: 'CartSummaryPaymentCard',
    props: ['products'],
    computed: {
        cart_total() {
            return this.$store.getters.cartTotal
        },
    },
}
</script>

<style></style>
