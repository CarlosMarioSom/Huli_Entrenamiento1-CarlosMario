<template>
    <div class="ContenedorDeSeguroPlanMedico">
        <SeguroPlanMedico
            v-for="(seguroMedico, index) in datosSegurosPlanesMedicos"
            :key="index"
            class="ContenedorDeSeguroPlanMedico__list"
            :datosSeguro="seguroMedico"
            :funcionEliminaSeguro="eliminaSeguro"
        ></SeguroPlanMedico>
        <v-btn depressed large color="blue" @click="agregaSeguroPlanMedico()">
            {{msjBtn}}
        </v-btn>
    </div>
</template>

<script>
import SeguroPlanMedico from './SeguroPlanMedico.vue';
export default {
    name: 'ContenedorDeSeguroPlanMedico',
    data() {
        return {
            msjBtn: '+ AGREGAR OTRO SEGURO O PLAN',
            /**
             * Este array tiene objetos:
             * {
             *    aseguradora: 'String',
             *    numeroPoliza: 'String'
             * }
             */
            datosSegurosPlanesMedicos: [],
        };
    },
    components: {
        SeguroPlanMedico
    },
    methods: {
        agregaSeguroPlanMedico() {
            this.datosSegurosPlanesMedicos.push({
            aseguradora: '',
            numeroPoliza: ''
            });
        },

        /**
         * Esta funcion es pasada por parametro
         * al componente hijo y borra el elemento 
         * del arreglo datosSegurosPlanesMedico que
         * corresponde al componente del que viene 
         * la accion
         * Entrada: un objeto de la forma
         * {
         *     aseguradora: 'String',
         *     numeroPoliza: 'String'
         * }
        */
        eliminaSeguro(seguro) {
            // -->aqui tuve duda con for(seguro in this.datosSegurosPlanesMedicos)
            for (let i = 0 ; i < this.datosSegurosPlanesMedicos.length ; i++) { 
                console.log('seguro: ', seguro);
                console.log('i: ', this.datosSegurosPlanesMedicos[i]);
                if (seguro === this.datosSegurosPlanesMedicos[i]) {
                    this.datosSegurosPlanesMedicos.splice(i, 1,);
                    break;
                }
            }
        }
    }
};
</script>

<style lang="scss">
.ContenedorDeSeguroPlanMedico {
    display: flex;
    flex-direction: column;
    align-items: center;

    &__list {
        max-width: 400px;
    }
}
</style>
