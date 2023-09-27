<template>
  <span v-if="selectedRecipe !== undefined && selectedRecipe.length > 0">
    <div class="textWrapper">
      <h4>{{ selectedRecipe[index]['title'] }}</h4>
    </div>
    <div class="imageWrapper">
      <img :src="selectedRecipe[index]['image']" alt="recipe image" />
    </div>
    <div class="viewControls">
      <view-controls @send-index="handleIndexing"></view-controls>
    </div>
  </span>
</template>

<script>
import ViewControls from '../components/ViewControls.vue'
export default {
  components: {
    ViewControls
  },

  data() {
    return {
      index: 0,
      selectedRecipe: undefined
    }
  },

  methods: {

    decrement() {
      this.index--
      if (this.index < 0) {
        this.index = this.selectedRecipe.length - 1
      }
    },
    increment() {
      this.index++
      if (this.index > this.selectedRecipe.length - 1) {
        this.index = 0
      }
    },

    handleIndexing(data) {
      if(data.className.baseVal === "rightArrow"){
        this.increment();
      } else if (data.className.baseVal === "leftArrow"){
        this.decrement();
      }
    },

    assignValues(data) {
        this.selectedRecipe = [];
        
        for(let i = 0; i < data['results'].length; i++){
            this.selectedRecipe.push(data['results'][i])
        }

        console.log(this.selectedRecipe.length)
    }
  },
  computed: {},
  created() {},
  mounted() {},
  beforeMount() {},
  beforeUpdate() {},
  updated() {},
  beforeUnmount() {},
  unmounted() {}
}
</script>

<style lang="scss" scoped></style>
