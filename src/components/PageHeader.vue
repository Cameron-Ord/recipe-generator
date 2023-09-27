
<template>
    <div class="headerWrapper">
        <nav class="navContainer">
            <h2 class="headerLogo">Home</h2>
            <h2 class="headerSubtext">Ipsum</h2>
        </nav>
        <span class="searchContainer">
            <input ref="textInput" placeholder="etc.." type="text" @keyup.enter="searchRecipes">
        </span>
    </div>
</template>

<script>
import axios from 'axios';
import { API_KEY } from '../../api-key';
    export default {
        components:{

        },

        data() {
            return {
                apiKey:API_KEY
            }
        },

        methods:{
            searchRecipes(){
                const queryInput = this.$refs.textInput.textContent;
                axios({
                    url: `https://api.spoonacular.com/recipes/complexSearch?query=${queryInput}`,
                    params:{
                        apiKey: this.apiKey
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
.headerWrapper{
    display: grid;
    
    grid-auto-flow: row;
    row-gap: 25px;
    >.searchContainer{
        display: grid;
        justify-items: center;
        >input{

        }
    }
    >.navContainer{
        display: grid;
        justify-items: center;
        grid-template-columns: 1fr 1fr;
    
        >.headerSubtext{
            text-align: center;
        }
        >.headerLogo{
            text-align: center;
        }
    }
}
</style>


