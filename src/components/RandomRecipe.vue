
<template>
    <article>
        <div class="recipeInfoContainer" v-if="recipeHolder !== undefined">
            <h3 class="RandomRecipeTitle">{{ recipeHolder['recipes'][0]['title'].toString() }}</h3>
            <img class="RandomRecipeImage" :src="recipeHolder['recipes'][0]['image']" alt="">
        </div>
        <div class="recipeInputContainer">
            <input ref="randomInput" class="randomInputTag" placeholder="vegetarian...desert.." type="text">
        </div>
    </article>
</template>

<script>
import axios from 'axios';
import { API_KEY } from '../../api-key';
    export default {
        components:{

        },

        data() {
            return {
                apiKey:API_KEY,
                recipeHolder : undefined
            }
        },

        methods:{

            requestRandomRecipe(){
                const inputTag = this.$refs.randomInputTag.textContent;
                axios({
                    url:`https://api.spoonacular.com/recipes/random?number=1&tags=${inputTag}`,
                    params:{
                        apiKey: this.apiKey
                    }
                }).then((response)=>{
                    this.recipeHolder = response['data'];
                    
                }).catch((error)=>{
                    error;
                })
            },

            getRandomRecipe(){
                axios({
                    url:`https://api.spoonacular.com/recipes/random`,
                    params:{
                        apiKey: this.apiKey
                    }
                }).then((response)=>{
                    this.recipeHolder = response['data'];
                }).catch((error)=>{
                    error;
                })
            }
        },
        computed:{

        },
        created(){

        },
        mounted(){
            this.getRandomRecipe();
        },
        beforeMount(){

        },
        beforeUpdate(){

        },
        updated(){

        },
        beforeUnmount(){

        },
        unmounted(){

        }

    }
</script>

<style lang="scss" scoped>

</style>


