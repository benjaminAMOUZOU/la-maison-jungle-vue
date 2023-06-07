<script setup>
import image from "../assets/logo.png"
import vue from "../assets/vue.svg"
import { ref } from "vue"

const title = ref("LA MAISON JUNGLE")
</script>

<template>
    <div class="row pt-4">
        <div class="col-lg-12">
            <div class="alert alert-success">
                <div class="d-flex justify-content-between">
                    <div>
                        <img :src="vue" alt="logo vue" class="logo" />
                    </div>
                    <div>
                        <img :src="image" alt="Logo" class="logo" />
                        <span className="fw-bold">{{ title }}</span>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
.logo {
    width: 32px;
    height: 32px;
}
</style>