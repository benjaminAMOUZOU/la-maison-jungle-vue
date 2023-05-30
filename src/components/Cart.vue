<script>
export default {
    data() {
        return {
            cart: []
        }
    },
    methods: {
        clearCart() {
            this.cart = [];
        }
    }
}
</script>

<template>
    <div class="col-lg-3 ms-0">
        <div class="card text-dark bg-light mb-3">
            <div class="card-header">Panier</div>
            <div class="card-body">
                <ul></ul>
                <p>
                    Total <span class="text-success"></span> FCFA
                </p>
                <button class="btn btn-outline-success btn-sm bouton" @click="clearCart">
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