<script>
import { plantList } from '../datas/plantList'
import PlantItem from './PlantItem.vue'
import Categorie from './Categorie.vue'

export default {
    data() {
        return {
            text: "Ici achetez toutes les plantes dont vous avez toujours rêvé !",
            plantFiltered: plantList,
        }
    },

    methods: {
        filtreCategorie(categorie) {
            if (categorie !== '') {
                this.plantFiltered = plantList.filter((plant) => {
                    return plant.category === categorie
                })
            } else {
                this.plantFiltered = plantList
            }
        },
    },

    components: { Categorie, PlantItem },

    props: ['cart'],

    emits: ['update-cart']
}
</script>

<template>
    <div class="col-lg-9">
        <p>{{ text }}</p>
        <div class="row">
            <Categorie @update-categorie="(categorie) => filtreCategorie(categorie)" />
        </div>
        <div class="row">
            <PlantItem @update-cart="(cart) => $emit('update-cart', cart)" v-for="plant in plantFiltered"
                :key="plant.id" :name="plant.name" :category="plant.category" :cover="plant.cover" :light="plant.light"
                :water="plant.water" :price="plant.price" :cart="cart" />
        </div>
    </div>
</template>

<style scoped></style>