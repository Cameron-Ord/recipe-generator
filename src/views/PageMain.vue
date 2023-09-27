<template>
    <main class="pageMain">
        <section class="heroSection">
            <hero-text></hero-text>
            <hero-image></hero-image>
        </section>
        <section>

        </section>
    </main>
</template>

<script>
import HeroText from '../components/HeroText.vue';
import HeroImage from '../components/HeroImage.vue';
    export default {
        data() {
            return {

            }
        },
        components:{
            HeroImage, HeroText
        }
    }
</script>

<style lang="scss" scoped>
.pageMain{
    display: grid;
    align-items: center;
    min-height: 100vh;
}
</style>