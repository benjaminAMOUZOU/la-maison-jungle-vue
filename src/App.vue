<script setup>
import Header from './components/Header.vue';
import Footer from './components/Footer.vue';
import Cart from './components/Cart.vue';
import ShoppingList from './components/ShoppingList.vue';
import { ref } from 'vue'

const cart = ref([])
const total = ref(0)

function updateCart(c) {
    cart.value = c
    total.value = cart.value.reduce((acc, plantType) => acc + plantType.amount * plantType.price, 0)
}

function clearCart() {
    cart.value = []
    total.value = 0
}
</script>

<template>
    <Header />
    <div className="row">
        <Cart :cart="cart" @clear-cart="clearCart()" :total="total" />
        <ShoppingList :cart="cart" @update-cart="(cart) => updateCart(cart)" />
    </div>
    <Footer />
</template>

<style scoped></style>
