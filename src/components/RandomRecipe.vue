
<template>
    <div>
        <input ref="randomInput" class="randomInputTag" placeholder="vegetarian...desert.." type="text">
    </div>
</template>

<script>
import axios from 'axios';
    export default {
        components:{

        },

        data() {
            return {
                
            }
        },

        methods:{

            requestRandomRecipe(){
                const inputTag = this.$refs.randomInputTag.textContent;
                axios({
                    url:`https://api.spoonacular.com/recipes/random?number=1&tags=${inputTag}`,
                    params:{
                        apiKey: 'mykey'
                    }
                }).then((response)=>{
                    response;
                }).catch((error)=>{
                    error;
                })
            },

            getRandomRecipe(){
                axios({
                    url:`https://api.spoonacular.com/recipes/random`,
                    params:{
                        apiKey: 'mykey'
                    }
                }).then((response)=>{
                    response;
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


