<script>
import image from "../assets/logo.png"

export default {
    data(){
        return {
            title: "LA MAISON JUNGLE",
            logo: image
        }
    }
}
</script>

<template>
    <div class="row pt-4">
        <div class="col-lg-12">
            <div class="alert alert-success">
                <div class="text-end">
                    <img :src="logo" alt="Logo" class="logo" />
                    <span className="fw-bold">{{title}}</span>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
.logo{
    width: 32px;
    height: 32px;
}
</style>