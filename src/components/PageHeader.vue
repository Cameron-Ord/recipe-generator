
<template>
    <div class="headerWrapper">
        <nav class="navContainer">
            <div class="logowrapper">
                <h2 class="headerLogo">Home</h2>
            </div>
            <div class="optionswrapper">
                <p class="headerSubtext">Signup</p>
                <p class="headerSubtext">Login</p>
            </div>
        </nav>
        <span class="searchContainer">
            <input ref="textInput" placeholder="Italian.. Asian.. etc..." type="text" @keyup.enter="searchRecipes">
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
                const queryInput = this.$refs.textInput.value;
                console.log(queryInput)
                axios({
                    url: `https://api.spoonacular.com/recipes/complexSearch?query=${queryInput}`,
                    params:{
                        apiKey: this.apiKey
                    }
                }).then((response)=>{
                    response;
                    this.$emit('query-response', response['data'])
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
        >.logowrapper{
            display: grid;
            align-items: center;
            >.headerLogo{
                text-align: center;
            }
        }

        >.optionswrapper{
            align-items: center;
            display: grid;
            grid-template-columns: 1fr 1fr;

            >.headerSubtext{
                padding-bottom: 2.5px;
                padding-top: 2.5px;
                padding-left: 5px;
                padding-right: 5px;
                text-align: center;
            }
        }
    }
}
</style>


