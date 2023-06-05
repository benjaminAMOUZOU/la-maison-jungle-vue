<script>
import CareScale from './CareSale.vue'

export default {
    props: ['name', 'water', 'category', 'light', 'price', 'cover'],
    components: { CareScale }
}
</script>

<template>
    <div class="col-lg-3">
        <div class="card mb-4">
            <img class="card-img-top" :src=cover alt="" />
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
                    <button class="btn btn-outline-success btn-sm">
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