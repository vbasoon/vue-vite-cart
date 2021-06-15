<template>
    <div>
        <div v-for="product in items" :key="product.id">
            {{ product.name }}
        </div>
    </div>
</template>

<script>
export default {
    name: 'CardItemCard',
    computed: {
        items() {
            return this.$store.getters.cartItems
        },
    },
}
</script>

<style></style>
