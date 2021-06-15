<template>
    <div class="cart-item-card">
        <div class="header font-bold">
            <h3>{{ product.name }}</h3>
            <h4>In Cart: {{ product.quantity }}</h4>
            <h4>Total Cost: {{ item_cost.toFixed(2) }}</h4>
        </div>
        <p>{{ description }}</p>
    </div>
</template>

<script>
export default {
    name: 'CartItemCard',
    props: ['product'],
    computed: {
        description() {
            return this.product.description.substring(0, 120)
        },
        item_cost() {
            return this.product.price * this.product.quantity
        },
    },
}
</script>

<style scoped lang="scss">
.cart-item-card {
    width: 50%;
    margin: 5%;
    background-color: #fff;
    box-shadow: 0 0 5px gray;
    padding: 10px;
    text-align: left;
}

.header {
    display: flex;
    justify-content: space-around;
}
</style>
