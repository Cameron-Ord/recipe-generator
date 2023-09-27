<template>
    <header class="pageHeader">
        <page-header @query-response="handleResponse"></page-header>
    </header>
    <main class="pageMain">
        <section class="heroSection">
            <article class="heroArticle">
                <hero-text></hero-text>
                <hero-image></hero-image>
            </article>
        </section>
        <section class="searchResults">
            <article class="resultsArticle">
                <search-results ref="searchresults"></search-results>
            </article>
        </section>
        <section class="randomRecipe">
            <article class="randomArticle">
                <random-recipe></random-recipe>
            </article>
        </section>
    </main>
    <footer>
        <page-footer></page-footer>
    </footer>
</template>

<script>
import SearchResults from '../components/SearchResults.vue';
import PageHeader from '../components/PageHeader.vue';
import PageFooter from '../components/PageFooter.vue';
import HeroText from '../components/HeroText.vue';
import HeroImage from '../components/HeroImage.vue';
import RandomRecipe from '../components/RandomRecipe.vue';
    export default {
        data() {
            return {

            }
        },
        methods:{
            handleResponse(data){
                console.log('assigning data..')
                this.$refs.searchresults.assignValues(data);

            }
        },
        components:{
            HeroImage,SearchResults,HeroText,RandomRecipe,PageFooter,PageHeader
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