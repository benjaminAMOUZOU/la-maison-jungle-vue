<script>
import Sun from '../assets/sun.svg'
import Water from '../assets/water.svg'

export default {
    data() {
        return {
            range: [1, 2, 3],
            sun: Sun,
            water: Water
        }
    },

    props: {
        scaleValue: Number,
        careType: String
    }
}
</script>

<template>
    <div>
        <span v-for="n in range">
            <span v-if="scaleValue >= n" :key=n>
                <img v-if="careType === 'light'" :src="sun" alt='sun-icon' />
                <img v-else :src=water alt='water-icon' />
            </span>
        </span>
    </div>
</template>