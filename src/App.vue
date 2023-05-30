<script>
import Header from './components/Header.vue';
import Footer from './components/Footer.vue';
import Cart from './components/Cart.vue';
import ShoppingList from './components/ShoppingList.vue';

export default {
    components: { Header, Footer, Cart, ShoppingList }

}
</script>

<template>
    <Header />
    <div className="row">
        <Cart cart={cart} updateCart={updateCart} />
        <ShoppingList cart={cart} updateCart={updateCart} />
    </div>
    <Footer />
</template>

<style scoped></style>
