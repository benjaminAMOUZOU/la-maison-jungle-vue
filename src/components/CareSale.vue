<script setup>
import Sun from "../assets/sun.svg"
import Water from "../assets/water.svg"
import { ref } from "vue"

const range = ref([1, 2, 3])
const props = defineProps({
    scaleValue: Number,
    careType: String
})
</script>

<template>
    <div>
        <span v-for="n in range">
            <span v-if="scaleValue >= n" :key="n">
                <img v-if="careType === 'light'" :src="Sun" alt="sun-icon" />
                <img v-else :src="Water" alt="water-icon" />
            </span>
        </span>
    </div>
</template>