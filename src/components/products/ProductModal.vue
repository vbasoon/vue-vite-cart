<template>
    <div
        class="modal-background"
        :class="{ show: active }"
        @click="$emit('close-modal')"
    >
        <div class="modal" :show="{ show: active }">
            <div class="modal-close" @click="$emit('close-modal')">x</div>
            <div v-if="product" class="product-details"></div>
        </div>
    </div>
</template>

<script>
export default {}
</script>

<style></style>
