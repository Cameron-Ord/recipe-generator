
<template>
    <span class="imageContainer">
        <img class="imageTag" ref="imageTag" :src="heroImages[index]" alt="placeholder">
    </span>
</template>

<script>
    export default {
        components:{

        },

        data() {
            return {
                heroImages : ['images/food1.jpg', 'images/food2.jpg', 'images/food3.jpg'],
                index : 0
            }
        },

        methods:{

        },
        computed:{

        },
        created(){
            this.index = Math.floor(Math.random()* this.heroImages.length);
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
.imageContainer{
    display: grid;
    align-items: center;
    >img{
        width: 100%;
        object-fit: cover;
        height: 400px;
    }
}
</style>


