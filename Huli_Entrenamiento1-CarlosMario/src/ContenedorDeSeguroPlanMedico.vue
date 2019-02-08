<template>
  <div id="ContenedorSeguros">
    <SeguroPlanMedico v-for="i in datosSegurosPlanesMedicos"></SeguroPlanMedico>
    <v-btn depressed large color="blue" @click="agregaSeguroPlanMedico()">{{
      msjBtn
    }}</v-btn>
  </div>
</template>

<script>
import SeguroPlanMedico from "./SeguroPlanMedico.vue";
export default {
  name: "ContenedorSeguros",
  data() {
    return {
      msjBtn: "+ AGREGAR OTRO SEGURO O PLAN",
      datosSegurosPlanesMedicos: []
    };
  },
  components: {
    SeguroPlanMedico
  },
  methods: {
    agregaSeguroPlanMedico: function() {
      this.datosSegurosPlanesMedicos.push("");
    }
  }
};
</script>

<style lang="scss"></style>
