<template>
    <main class="pageMain">
        <section class="heroSection">
            <article class="heroArticle">
                <hero-text></hero-text>
                <hero-image></hero-image>
            </article>
        </section>
        <section>
            <random-recipe></random-recipe>
        </section>
    </main>
</template>

<script>
import HeroText from '../components/HeroText.vue';
import HeroImage from '../components/HeroImage.vue';
import RandomRecipe from '../components/RandomRecipe.vue';
    export default {
        data() {
            return {

            }
        },
        components:{
            HeroImage, HeroText,RandomRecipe
        }
    }
</script>

<style lang="scss" scoped>
.pageMain{
    display: grid;
    align-items: center;
    min-height: 100vh;
    >.heroArticle{
        display: grid;
        align-items: center;
    }
}
</style>