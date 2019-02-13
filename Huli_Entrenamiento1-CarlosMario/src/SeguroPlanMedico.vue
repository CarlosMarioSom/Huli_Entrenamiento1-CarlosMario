<template>
  <div id="SeguroPlanMedico">
    <v-container>
      <v-layout>
        <v-flex>
          <h3>{{ translations.heart }}</h3>
        </v-flex>
        <v-flex>
          <h3>{{ translations.mensajePrincipal }}</h3>
        </v-flex>
        <v-flex>
          <v-btn @click="$emit('remove-insurance')" flat small>X</v-btn>
        </v-flex>
      </v-layout>
    </v-container>
    <v-container>
      <v-layout>
        <v-flex>
          <v-text-field
            placeholder="Aseguradora/Institucion"
            v-model="datos.aseguradora"
          ></v-text-field>
        </v-flex>
        <v-flex>
          <v-text-field
            class="SeguroPlanMedico__inputNumber"
            placeholder="Poliza/numero de afiliado"
            v-model="datos.numeroPoliza"
          ></v-text-field>
        </v-flex>
      </v-layout>
    </v-container>
  </div>
</template>

<script>
export default {
	name: 'SeguroPlanMedico',
	props: {
		datos: {
            type: Object, 
            default() {
                return new InsuranceEntity()
            }
        },
	},
	data() {
		return {
        translations : {
          mensajePrincipal: 'Seguro o plan medico',
			    heart: '<3',
        }
			
		};
	},
};
</script>

<style lang="scss">
.SeguroPlanMedico {
	&__inputNumber {
    	margin-left: 10px;
	}
}
</style>
