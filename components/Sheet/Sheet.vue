<template>
    <v-container>
        <v-row>
          <v-col
            cols="12"
            sm="2"
          >
            <v-sheet
              color="#CFD8DC"
              rounded="lg"
              min-height="268"
            >
            </v-sheet>
          </v-col>

          <v-col
            cols="12"
            sm="8"
          >
            <v-sheet
              color="#CFD8DC"
              min-height="70vh"
              rounded="lg"
            >
            <nuxt-child></nuxt-child>
            </v-sheet>
          </v-col>
        </v-row>
    </v-container>
</template>

<script>
export default {
}
</script>

<style>

</style>