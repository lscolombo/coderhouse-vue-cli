<template>
  <div id="app">
  <div class="table-options">
        <h4 class="text-primary">Estilos de tabla</h4>
        <div class="form-check">
            <input class="form-check-input" type="checkbox" id="check-dark-mode" @click="toggleDarkMode">
            <label class="form-check-label" for="check-dark-mode">
              Modo oscuro
            </label>
        </div>
        <div class="form-check">
            <input class="form-check-input" type="checkbox" id="check-striped-mode" @click="toggleStripedMode">
            <label class="form-check-label" for="check-striped-mode">
              Modo a rayas
            </label>
        </div>
    </div>
    <div>
        <NutritionFactsTable :foods="foods" :class="darkMode + ' ' + stripedMode" />
    </div>
  </div>
</template>

<script>
import NutritionFactsTable from './components/NutritionFactsTable.vue'

export default {
  name: 'App',
  components: {
    NutritionFactsTable
  },
  data() { return {
        darkModeActive: false,
        darkMode: "",
        stripedModeActive: false,
        stripedMode: "",
        foods: [
            {
                "ID": 1,
                "CAL": "740",
                "FAT": "41",
                "SFAT": "16",
                "TFAT": "1.5",
                "CHOL": "125",
                "SALT": "1480",
                "CARB": "51",
                "FBR": "4",
                "SGR": "14",
                "PRO": "40",
                "ITEM": "Bacon Clubhouse Burger 9.7 oz (274 g)",
                "CATEGORY": "BURGERSANDWICH"
            },
            {
                "ID": 2,
                "CAL": "610",
                "FAT": "26",
                "SFAT": "8",
                "TFAT": "0",
                "CHOL": "125",
                "SALT": "1750",
                "CARB": "50",
                "FBR": "3",
                "SGR": "14",
                "PRO": "45",
                "ITEM": "Premium Grilled Chicken Bacon Clubhouse Sandwich 10 oz (285 g)",
                "CATEGORY": "BURGERSANDWICH"
            },
            {
                "ID": 3,
                "CAL": "790",
                "FAT": "40",
                "SFAT": "11",
                "TFAT": "0.5",
                "CHOL": "110",
                "SALT": "1620",
                "CARB": "67",
                "FBR": "5",
                "SGR": "15",
                "PRO": "40",
                "ITEM": "Premium Buttermilk Crispy Chicken Bacon Clubhouse Sandwich 10.1 oz (287 g)",
                "CATEGORY": "BURGERSANDWICH"
            },
            {
                "ID": 4,
                "CAL": "370",
                "FAT": "17",
                "SFAT": "3.5",
                "TFAT": "0",
                "CHOL": "40",
                "SALT": "650",
                "CARB": "40",
                "FBR": "2",
                "SGR": "5",
                "PRO": "14",
                "ITEM": "McChicken \u00ae 5.1 oz (144 g)",
                "CATEGORY": "BURGERSANDWICH"
            },
            {
                "ID": 5,
                "CAL": "370",
                "FAT": "17",
                "SFAT": "3.5",
                "TFAT": "0",
                "CHOL": "40",
                "SALT": "850",
                "CARB": "41",
                "FBR": "2",
                "SGR": "5",
                "PRO": "14",
                "ITEM": "Buffalo Ranch McChicken 5.2 oz (148 g)",
                "CATEGORY": "BURGERSANDWICH"
            },
            {
                "ID": 6,
                "CAL": "440",
                "FAT": "21",
                "SFAT": "5",
                "TFAT": "0",
                "CHOL": "55",
                "SALT": "1120",
                "CARB": "41",
                "FBR": "2",
                "SGR": "6",
                "PRO": "20",
                "ITEM": "Bacon Buffalo Ranch McChicken 5.7 oz (162 g)",
                "CATEGORY": "BURGERSANDWICH"
            },
            {
                "ID": 7,
                "CAL": "490",
                "FAT": "25",
                "SFAT": "7",
                "TFAT": "0",
                "CHOL": "70",
                "SALT": "1120",
                "CARB": "43",
                "FBR": "2",
                "SGR": "6",
                "PRO": "22",
                "ITEM": "Bacon Cheddar McChicken 6.1 oz (172 g)",
                "CATEGORY": "BURGERSANDWICH"
            }
        ]}
    }, 
    methods: {
       toggleDarkMode() {
            this.darkModeActive = !this.darkModeActive
            this.darkModeActive ? (this.darkMode = "table-dark") : (this.darkMode="")
        },
        toggleStripedMode() {
            this.stripedModeActive = !this.stripedModeActive
            this.stripedModeActive ? (this.stripedMode = "table-striped") : (this.stripedMode="")
        }
    }
}
</script>

<style>
@import './assets/css/styles.css';
</style>
