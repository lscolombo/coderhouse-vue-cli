<template lang="html">

    <table class="table">
            <thead>
                <tr>
                    <th>Nombre</th>
                    <th>Calorías</th>
                    <th>Carbohidratos</th>
                    <th>Grasas</th>
                </tr>
            </thead>
            <tbody>
            <NutritionFactsTableRow
            v-for="food in foods"
            :key="food.ID"
            :name="food.ITEM"
            :calories="food.CAL"
            :carbs="food.CARB"
            :fat="food.FAT"
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
