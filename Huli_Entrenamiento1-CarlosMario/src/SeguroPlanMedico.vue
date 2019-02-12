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
          <v-btn @click="funcionEliminaSeguro(datosSeguro)" flat small>X</v-btn>
        </v-flex>
      </v-layout>
    </v-container>
    <v-container>
      <v-layout>
        <v-flex>
          <v-text-field
            id="in_Aseguradora"
            placeholder="Aseguradora/Institucion"
            v-model="datosSeguro.aseguradora"
          ></v-text-field>
        </v-flex>
        <v-flex>
          <v-text-field
            class="SeguroPlanMedico__inputNumber"
            id="in_Numero"
            placeholder="Poliza/numero de afiliado"
            v-model="datosSeguro.numeroPoliza"
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
		datosSeguro: {
            type: Object, 
            default() {
                return {
                    aseguradora: '',
                    numeroPoliza: '',
                }
                
            }
        },
        funcionEliminaSeguro: {
            type: Function,
            default() {
                () => {alert('Funcion no pasada por parametro')}
            }
        },
	},
	data() {
		return {
			msjPrincipal: 'Seguro o plan medico',
			heart: '<3',
		};
	},
	methods: {},
	components: {}
};
</script>

<style lang="scss">
.SeguroPlanMedico {
	&__inputNumber {
    	margin-left: 10px;
	}
}
</style>
