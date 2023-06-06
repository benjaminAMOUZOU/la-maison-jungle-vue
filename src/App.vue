<script>
import Header from './components/Header.vue';
import Footer from './components/Footer.vue';
import Cart from './components/Cart.vue';
import ShoppingList from './components/ShoppingList.vue';

export default {
    data() {
        return {
            cart: [],
            total: 0
        }
    },

    components: { Header, Footer, Cart, ShoppingList },

    methods: {
        updateCart(cart) {
            this.cart = cart
            this.total = this.cart.reduce((acc, plantType) => acc + plantType.amount * plantType.price, 0)
        },

        clearCart() {
            this.cart = []
            this.total = 0
        }
    }
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
