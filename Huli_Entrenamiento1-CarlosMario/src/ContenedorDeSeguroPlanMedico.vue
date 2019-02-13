<template>
    <div class="ContenedorDeSeguroPlanMedico">
        <SeguroPlanMedico
            class="ContenedorDeSeguroPlanMedico__list"
            v-for="(seguroMedico, index) in datosSegurosMedicos"
            :key="index"
            :datos="seguroMedico"
            @remove-insurance="removeInsurance(index)"
        ></SeguroPlanMedico>
        <v-btn depressed large color="blue" @click="agregaSeguroPlanMedico()">
            {{translations.buttons.add}}
        </v-btn>
    </div>
</template>

<script>
import SeguroPlanMedico from './SeguroPlanMedico.vue';
import InsuranceEntity from './insurance_entity.js';
export default {
    name: 'SegurosMedicos',
    data() {
        return {
            translations : {
                buttons : {
                    add : "+ AGREGAR OTRO SEGURO O PLAN"
                },
            },
            /**
             * Este 
             * array tiene objetos:
             * {
             *    aseguradora: 'String',
             *    numeroPoliza: 'String'
             * }
             */
            datosSegurosMedicos: [],
        };
    },
    components: {
        SeguroPlanMedico,
    },
    methods: {
        agregaSeguroPlanMedico() {
            this.datosSegurosMedicos.push(new InsuranceEntity());
        },

        /*
         * Borra elemento del arreglo en la posicion del index
         Input: index del elemento que hay que borrar (el que asigna v-for)
         */
        removeInsurance(index) {
            this.datosSegurosMedicos.splice(index,1);
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
