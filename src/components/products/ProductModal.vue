<template>
    <div
        class="modal-background w-full h-screen fixed left-0 top-0"
        :class="{ show: active }"
        @click="$emit('close-modal')"
    >
        <div class="modal" :show="{ show: active }">
            <div class="modal-close" @click="$emit('close-modal')">x</div>
            <div v-if="product" class="product-details">
                <h3 class="text-center">{{ product.name }}</h3>
                <p class="description">{{ product.description }}</p>
                <h3 class="text-center">${{ product.price.toFixed(2) }}</h3>
                <div v-if="product_total" class="cart-total">
                    <h3>In Cart</h3>
                    <h4>{{ product_total }}</h4>
                </div>
                <div class="buttons-cart">
                    <button class="remove">Remove</button>
                    <button class="add">Add</button>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: ['product', 'active'],
    computed: {
        product_total() {
            return 56.0
        },
    },
}
</script>

<style lang="scss">
.modal-background {
    background-color: rgba(124, 124, 124, 0.5);
    z-index: 100;
    display: none;
    transition: display 0.5s;

    &.show {
        display: block;
    }
}
</style>
