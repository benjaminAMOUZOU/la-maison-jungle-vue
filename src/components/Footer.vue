<script>
export default {
    data() {
        mail: ""
    },
    methods:{
        checkValue(){
            if(!this.mail.includes('@')){
                alert("Votre adresse email n'est pas une adresse valide !");
            }
        }
    }

}
</script>

<template>
    <div class="row">
        <div class="offset-lg-5 col-lg-3 mb-3 mt-3 text-center">
            <p>Pour les passionné-e-s des plantes</p>
            <p>Laissez-nous votre mail:</p>
            <input type="text" v-model=mail placeholder="Ecrivez votre mail" class="form-control form-control-sm" @blur="checkValue"/>
        </div>
    </div>
</template>