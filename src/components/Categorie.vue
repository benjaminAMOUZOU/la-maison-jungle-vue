<script>
export default {
    data() {
        return {
            categorie: ""
        }
    },
    methods: {
        updateCategorieEvent() {
            this.$emit('update-categorie', this.categorie)
        },
        resetCategorie() {
            this.categorie = ""
        }
    },
    watch: {
        categorie(newCategorie, oldCategorie) {
            this.$emit('update-categorie', newCategorie)
        }
    }
}

</script>

<template>
    <div class="col-lg-12 text-center">
        <div class="row mb-3">
            <div class="offset-lg-3 col-lg-4 mt-2 me-0">
                <select class="form-select form-select-sm" aria-label="Default select example" v-model=categorie>
                    <!-- @change=updateCategorieEvent -->
                    <option value="" no-selection-option>Choisissez une catégorie</option>
                    <option value="Classique">Classique</option>
                    <option value="Extérieur">Extérieur</option>
                    <option value="Plante grasse">Plante grasse</option>
                </select>
            </div>
            <div class="col-lg-2 mt-2">
                <button class="btn btn-outline-success btn-sm" @click=resetCategorie>
                    Reinitialiser
                </button>
            </div>
        </div>
    </div>
</template>