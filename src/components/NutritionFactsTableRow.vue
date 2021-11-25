<template lang="html">

    <tr>
            <td>{{name}}</td>
            <td>{{calories}}</td>
            <td>{{carbs}}</td>
            <td>{{fat}}</td>
        </tr>

</template>

<script lang="js">

  export default  {
    name: 'NutritionFactsTableRow',
    props: {
        name: String,
        calories: String,
        carbs: String,
        fat: String
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
  .nutrition-facts-table-row {

  }
</style>
