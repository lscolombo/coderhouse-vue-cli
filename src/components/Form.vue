<template>
  <v-container>
    <v-form v-model="valid" ref="form">
      <v-text-field
        v-model="name"
        label="Nombre"
        :rules="nameRules"
        required
      ></v-text-field>

   

      <v-row>
        <v-col>
          <v-checkbox
            v-model="ingredientes"
            label="Tomate"
            value="Tomate"
            :rules="ingredientesRules"
          ></v-checkbox>
        </v-col>
        <v-col>
          <v-checkbox
            v-model="ingredientes"
            label="Lechuga"
            value="Lechuga"
            :rules="ingredientesRules"

          ></v-checkbox>
        </v-col>
        <v-col>
          <v-checkbox
            v-model="ingredientes"
            label="Cebolla"
            value="Cebolla"
            :rules="ingredientesRules"

          ></v-checkbox>
        </v-col>
        <v-col>
          <v-checkbox
            v-model="ingredientes"
            label="Queso"
            value="Queso"
            :rules="ingredientesRules"

          ></v-checkbox>
        </v-col>
      </v-row>

      <v-row>
        <v-radio-group v-model="vegan">
          <v-radio label="Sí" value="Sí"></v-radio>
          <v-radio label="No" value="No"></v-radio>
          <v-radio label="No sé" value="No sé"></v-radio>
        </v-radio-group>
      </v-row>

         <v-text-field
        type="number"
        v-model.number="calories"
        label="Calorías"
        :rules="caloriesRules"
        required
      ></v-text-field>
      <v-btn color="accent" class="mr-4" @click="addItem" :disabled="!valid">
        ENVIAR
      </v-btn>
    </v-form>
  </v-container>
</template>

<script>
export default {
  name: "Form",
  data() {
    return {
      valid: false,
      calories: null,
      ingredientes: [],
      vegan: null,
      name: null,
      nameRules: [(v) => !!v || "El nombre es requerido"],
      caloriesRules: [(v) => !!v || "Las calorías son requeridas"],
      ingredientesRules: [(v) => v.length !== 0 || "Debe elegir al menos un ingrediente"],
    };
  },
  methods: {
    addItem: function () {
        this.validate();
      let food = {
        ID: 8,
        CAL: this.calories,
        INGR: this.ingredientes.toString(),
        VEGAN: this.vegan,
        ITEM: this.name,
      };
      this.$emit("itemAdded", food);
      this.calories = null;
      this.ingredientes = [];
      this.vegan = null;
      this.name = null;
    },
    validate() {
      this.$refs.form.validate();
    },
  },
};
</script>

<style scoped>
a {
  color: #42b983;
}
label {
  margin-left: 0.5em !important;
}
</style>
