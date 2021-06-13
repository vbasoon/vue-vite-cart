<template>
    <div
        class="modal-background w-full h-screen fixed left-0 top-0"
        :class="{ show: active }"
        @click="$emit('close-modal')"
    >
        <div class="modal" :class="{ show: active }">
            <div class="modal-close px-3" @click="$emit('close-modal')">x</div>
            <div
                v-if="product"
                class="product-details flex flex-col justify-center"
            >
                <h3 class="text-center font-bold text-2xl">
                    {{ product.name }}
                </h3>
                <p class="description p-5 leading-6 text-left">
                    {{ product.description }}
                </p>
                <h3 class="text-center font-bold">
                    ${{ product.price.toFixed(2) }}
                </h3>
                <div v-if="product_total" class="cart-total">
                    <h3 class="text-center font-bold">In Cart</h3>
                    <h4 class="text-center font-bold">{{ product_total }}</h4>
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

.modal {
    width: 95vw;
    height: 100vh;
    background-color: #fff;
    position: fixed;
    top: 0;
    left: -105vw;
    padding: 15px;
    transition: left 0.5s;
    z-index: 101;
    overflow-y: scroll;

    &.show {
        left: 0;
    }
}

.modal-close {
    font-size: 1.5rem;
    border-radius: 5px;
    right: 10px;
    border: 2px solid grey;
    color: grey;
    float: right;
    cursor: pointer;

    &:hover {
        background-color: lightgray;
    }
}

.buttons-cart {
    button {
        width: 150px;
        border: none;
        padding: 10px;
        border-radius: 5px;
        margin: 0 5px 50px 5px;
        cursor: pointer;
        background-color: lightgray;
    }
}

@media (min-width: 500px) {
    .modal {
        width: 450px;
    }
}
</style>
