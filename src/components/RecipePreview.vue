<template>
  <span>
    <h3>{{ recipeHolder[index] }}</h3>
    <img :src="recipeHolder[index]" alt="your selected recipe" />
  </span>
</template>

<script>
import axios from 'axios'
import Cookies from 'vue-cookies'
import { API_KEY } from '../../api-key'
export default {
  components: {},

  data() {
    return {
      apiKey: API_KEY,
      index: 0,
      recipeHolder: undefined
    }
  },

  methods: {
    decrement() {
      this.index--
      if (this.index < 0) {
        this.index = this.recipeHolder.length - 1
      }
    },
    increment() {
      this.index++
      if (this.index > this.recipeHolder.length - 1) {
        this.index = 0
      }
    },
    recipeSetter() {
      const recipeID = Cookies.get('recipeID')
      axios({
        url: `https://api.spoonacular.com/recipes/${recipeID}`,
        params: {
          apiKey: this.apiKey
        }
      })
        .then((response) => {
          this.recipeHolder = []
          for (let i = 0; i < response['data'].length; i++) {
            this.recipeHolder.push(response['data'].length)
          }
          Cookies.remove('recipeID')
          response
        })
        .catch((error) => {
          error
        })
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
