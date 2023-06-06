<script>
export default {

    props: ['cart', 'total'],

    emits: ['clear-cart']
}
</script>

<template>
    <div class="col-lg-3 ms-0">
        <div class="card text-dark bg-light mb-3">
            <div class="card-header">Panier</div>
            <div class="card-body">
                <ul>
                    <li v-for="c in cart">
                        {{ c.name }} - {{ c.price * c.amount }} FCFA
                    </li>
                </ul>
                <p>
                    Total <span class="text-success">{{ total }}</span> FCFA
                </p>
                <button class="btn btn-outline-success btn-sm bouton" @click="$emit('clear-cart')">
                    Vider le panier
                </button>
            </div>
        </div>
    </div>
</template>

<style scoped>
.bouton {
    width: 100%;
}
</style>