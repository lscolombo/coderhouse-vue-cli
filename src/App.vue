<template>
  <v-app>
    <v-app-bar app color="primary" dark>
      <div class="d-flex align-center">
        <v-img
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png"
          transition="scale-transition"
          width="40"
        />

        <v-img
          alt="Vuetify Name"
          class="shrink mt-1 hidden-sm-and-down"
          contain
          min-width="100"
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-name-dark.png"
          width="100"
        />
      </div>

      <v-spacer></v-spacer>

      <v-btn
        href="https://github.com/vuetifyjs/vuetify/releases/latest"
        target="_blank"
        text
      >
        <span class="mr-2">Latest Release</span>
        <v-icon>mdi-open-in-new</v-icon>
      </v-btn>
    </v-app-bar>

    <v-main>
      <div class="row">
        <div class="col-sm">
          <Form @itemAdded="addItem" />
        </div>
        <div class="col-sm">
          <NutritionFactsTable :foods="foods" />
        </div>
      </div>
    </v-main>
  </v-app>
</template>

<script>
import NutritionFactsTable from "./components/NutritionFactsTable.vue";
import Form from "./components/Form.vue";

export default {
  name: "App",
  components: {
    NutritionFactsTable,
    Form,
  },
  data() {
    return {
      darkModeActive: false,
      darkMode: "",
      stripedModeActive: false,
      stripedMode: "",
      foods: [
        {
          ID: 1,
          CAL: 740,
          INGR: "Tomate, Lechuga",
          VEGAN: "Sí",
          FAT: "41",
          SFAT: "16",
          TFAT: "1.5",
          CHOL: "125",
          SALT: "1480",
          CARB: "51",
          FBR: "4",
          SGR: "14",
          PRO: "40",
          ITEM: "Bacon Clubhouse Burger 9.7 oz (274 g)",
          CATEGORY: "BURGERSANDWICH",
        },
        {
          ID: 2,
          CAL: 610,
          INGR: "Tomate, Lechuga",
          VEGAN: "Sí",
          FAT: "26",
          SFAT: "8",
          TFAT: "0",
          CHOL: "125",
          SALT: "1750",
          CARB: "50",
          FBR: "3",
          SGR: "14",
          PRO: "45",
          ITEM: "Premium Grilled Chicken Bacon Clubhouse Sandwich 10 oz (285 g)",
          CATEGORY: "BURGERSANDWICH",
        },
        {
          ID: 3,
          CAL: 790,
          INGR: "Tomate, Lechuga",
          VEGAN: "Sí",
          FAT: "40",
          SFAT: "11",
          TFAT: "0.5",
          CHOL: "110",
          SALT: "1620",
          CARB: "67",
          FBR: "5",
          SGR: "15",
          PRO: "40",
          ITEM: "Premium Buttermilk Crispy Chicken Bacon Clubhouse Sandwich 10.1 oz (287 g)",
          CATEGORY: "BURGERSANDWICH",
        },
      ],
    };
  },
  methods: {
    addItem: function (food) {
      food.ID = this.lastID() + 1;
      console.log(food);
      this.foods.push(food);
    },
    lastID: function () {
      let ids = this.foods.map((food) => food.ID);
      return Math.max(...ids);
    },
  },
};
</script>
