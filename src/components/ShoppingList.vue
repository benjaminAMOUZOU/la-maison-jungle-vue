<script>
export default {
    data() {
        return {
            text: "Ici achetez toutes les plantes dont vous avez toujours rêvé !",
            categorie: "",
        }
    },
    methods: {

    }
}
</script>

<template>
    <div class="col-lg-9">
        <p>{{text}}</p>
        <div class="row">
            <Categorie categorie={categorie} updateCategorie={updateCategorie} />
        </div>
        <div class="row">
            <PlantItem key="" id="" name="" category="" cover="" light="" water="" price="" cart="" updateCart="" />
        </div>
    </div>
</template>

<style scoped></style>