<template lang="html">

    <table class="table">
            <thead>
                <tr>
                    <th>Nombre</th>
                    <th>Calorías</th>
                    <th>Ingredientes</th>
                    <th>Apto vegano</th>
                </tr>
            </thead>
            <tbody>
            <NutritionFactsTableRow
            v-for="food in foods"
            :key="food.ID"
            :name="food.ITEM"
            :calories="food.CAL"
            :ingredients="food.INGR"
            :vegan="food.VEGAN"
            />
            </tbody>
        </table>

</template>

<script lang="js">
import NutritionFactsTableRow from './NutritionFactsTableRow.vue'

  export default  {
    name: 'NutritionFactsTable',
    components: {
      NutritionFactsTableRow
    },
    props: {
        foods: Array,
    },
    mounted () {

    },
    data () {
      return {

      }
    },
    methods: {

    },
    computed: {

    }
}


</script>

<style scoped lang="scss">
  .nutrition-facts-table {

  }
</style>
