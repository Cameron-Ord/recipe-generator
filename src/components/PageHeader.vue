
<template>
    <div>
        <nav>
            <h2>Home</h2>
            <h2>Ipsum</h2>
        </nav>
        <span>
            <input ref="textInput" placeholder="etc.." type="text" @keyup.enter="searchRecipes">
        </span>
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
            searchRecipes(){
                const queryInput = this.$refs.textInput.textContent;
                axios({
                    url: `https://api.spoonacular.com/recipes/complexSearch?query=${queryInput}`,
                    params:{
                        apiKey: 'placeholder'
                    }
                }).then((response)=>{
                    response;
                }).catch((error=>{
                error
            }));
        }
        },
        computed:{

        },
        created(){

        },
        mounted(){

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


