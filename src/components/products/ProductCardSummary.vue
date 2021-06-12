<template>
    <div class="card">
        <h3 class="font-bold text-2xl">{{ product.name }}</h3>
        <h5 class="price">Price: ${{ product.price.toFixed(2) }}</h5>
        <p class="description">Description: {{ description }}</p>
        <p class="text-muted underline mb-4">
            Category: {{ product.category }}
        </p>
        <button
            class="
                view-product-button
                border
                bg-green-500
                text-white
                rounded-3xl
                px-4
                py-2
            "
            @click="$emit('view-product', product)"
        >
            View Product
        </button>
    </div>
</template>
<script>
export default {
    props: ['product'],
    computed: {
        description() {
            return this.product.description.substring(0, 150)
        },
    },
}
</script>

<style lang="scss">
.card {
    width: 80%;
    margin: 10%;
    padding: 10px;
    border-radius: 5px;
    background-color: #fff;
    box-shadow: 0 0 5px gray;

    h5.price {
        color: gray;
    }

    p.description {
        font-size: 0.85rem;
    }

    p.text-muted {
        color: gray;
    }

    button.view-product-button {
        border: none;
        cursor: pointer;
        &:active {
            border: none;
        }
    }
}

@media (min-width: 500px) {
    .card {
        width: 350px;
        margin: 10px;
    }
}
</style>
