<script setup>
import CareScale from "./CareSale.vue"

const props = defineProps(['name', 'water', 'category', 'light', 'price', 'cover', 'cart'])
const emit = defineEmits(['update-cart'])

function addToCart(name, price) {
    const currentPlantAdded = props.cart.find((plant) => plant.name === name)

    if (currentPlantAdded) {
        const cartFilterdPlantAdded = props.cart.filter((plant) => plant.name !== name)

        emit('update-cart', [
            ...cartFilterdPlantAdded,
            { name, price, amount: currentPlantAdded.amount + 1 },
        ])

    } else {
        emit('update-cart', [...props.cart, { name, price, amount: 1 }])
    }
}
</script>

<template>
    <div class="col-lg-3">
        <div class="card mb-4">
            <img class="card-img-top" :src="cover" alt="Image de la plante" />
            <div class="card-body">
                <div class="row">
                    <div class="col">
                        <h5 class="card-title">{{ name }}</h5>
                    </div>
                    <div class="col text-end">
                        <CareScale careType="water" :scaleValue="water" />
                    </div>
                </div>

                <div class="row">
                    <div class="col">
                        <p class="card-text">{{ category }}</p>
                    </div>
                    <div class="col text-end">
                        <CareScale careType="light" :scaleValue="light" />
                    </div>
                </div>

                <div class="text-start mt-2">
                    <span class="text-danger">{{ price.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ".") }} FCFA</span>
                </div>

                <div class="text-end mt-2">
                    <button class="btn btn-outline-success btn-sm" @click="addToCart(name, price)">
                        Ajouter
                    </button>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
img {
    width: 100%;
    height: 221px;
}
</style>