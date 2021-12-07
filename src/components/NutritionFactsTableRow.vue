<template lang="html">
        <tr>
            <td>{{name}}</td>
            <td>{{calories}}</td>
            <td>{{ingredients}}</td>
            <td>{{vegan}}</td>
        </tr>

</template>

<script lang="js">

  export default  {
    name: 'NutritionFactsTableRow',
    props: {
        name: String,
        calories: Number,
        ingredients: String,
        vegan: String
    }
}


</script>

<style scoped lang="scss">
.nutrition-facts-table-row {
}
</style>
