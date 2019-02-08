<template>
  <div id="SeguroPlanMedico">
    <v-container>
      <v-layout>
        <v-flex>
          <h3>{{ heart }}</h3>
        </v-flex>
        <v-flex>
          <h3>{{ msjPrincipal }}</h3>
        </v-flex>
        <v-flex>
          <v-btn flat small>X</v-btn>
        </v-flex>
      </v-layout>
    </v-container>
    <v-container>
      <v-layout>
        <v-flex>
          <v-autocomplete
            id="in_Aseguradora"
            placeholder="Aseguradora/Institucion"
          ></v-autocomplete>
        </v-flex>
        <v-flex>
          <v-text-field
            id="in_Numero"
            placeholder="Poliza/numero de afiliado"
          ></v-text-field>
        </v-flex>
      </v-layout>
    </v-container>
  </div>
</template>

<script>
export default {
  name: "SeguroPlanMedico",
  data() {
    return {
      msjPrincipal: "Seguro o plan medico",
      heart: "<3"
    };
  },
  components: {}
};
</script>

<style lang="scss">
h3 {
  color: black;
}
</style>
