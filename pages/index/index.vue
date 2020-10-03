<template>
  <v-form ref="form" v-model="valid" lazy-validation>
    <v-text-field
      v-model="name"
      :counter="10"
      :rules="nameRules"
      label="Name"
      required
    ></v-text-field>

    <v-text-field
      v-model="image"
      :rules="imageeRules"
      label="image url"
      required
    ></v-text-field>

    <v-select
      v-model="select"
      :items="items"
      :rules="[(v) => !!v || 'La classe du servant est requise.']"
      label="classe"
      required
    ></v-select>

    <v-text-field
      v-model="personnality"
      :rules="personalityRules"
      label="personnalité"
      required
    ></v-text-field>

              <v-row no-gutters>
                <v-col
                  v-for="i in 6"
                  :key="i"
                  cols="12"
                  md="2"
                >
              <v-text-field class="stat-field"
                :label="labels[i - 1]"
                v-model="stats[i - 1]"
                flat
              >
              </v-text-field>
                </v-col>
              </v-row>

    <v-btn :disabled="!valid" class="mr-4" @click="validate">
      Validate
    </v-btn>

    <v-btn class="mr-4" @click="reset"> Reset Form </v-btn>

    <v-btn @click="resetValidation"> Reset Validation </v-btn>
  </v-form>
</template>

<script>
export default {
  data: () => ({
    valid: true,
    name: "",
    nameRules: [
      (v) => !!v || "Le nom est requis.",
      (v) =>
        (v && v.length <= 32) || "Le nom ne doit pas dépasser 32 caractères.",
    ],
    imageRules: [(v) => !!v || "Une image est requise."],
    select: null,
    items: [
      "Saber",
      "Archer",
      "Lancer",
      "Assassin",
      "Rider",
      "Caster",
      "Berserker",
      "Extra-class",
    ],
    stats: [],
    labels: ["FOR", "AGI", "CHANCE", "END", "MANA", "NP"],
  }),

  methods: {
    validate() {
      this.$refs.form.validate();
    },
    reset() {
      this.$refs.form.reset();
    },
    resetValidation() {
      this.$refs.form.resetValidation();
    },
  },
};
</script>

<style>
</style>