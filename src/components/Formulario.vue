<script setup>
    import { reactive } from 'vue'
    import Alertas from './Alertas.vue'

    const alerta = reactive({
        tipo:'',
        mensaje:''
    })

    const emit = defineEmits(['update:nombre', 'update:propietario', 'update:email', 'update:alta', 'update:sintomas', 'guardar-paciente'])

    const props = defineProps({
        nombre: {
            type: String,
            required: true
        },
        propietario: {
            type: String,
            required: true
        },
        email: {
            type: String,
            required: true
        },
        alta: {
            type: String,
            required: true
        },
        sintomas: {
            type: String,
            required: true
        }
    })

    const validar = () => {
        if(Object.values(props).includes('')){
            alerta.mensaje = 'Todos los campos son obligatorios'
            alerta.tipo = 'error'
            return
        }

        emit('guardar-paciente')
    }

</script>

<template>
    <div class="md:w-1/2">
        <h2 class="font-black text-3xl text-center">Seguimiento pacientes</h2>
        <p class="text-lg mt-5 text-center mb-10">
            Añade pacientes y
            <span class="text-indigo-600 font-bold">adminístralos</span>
        </p>

       
        <form 
            class="bg-white shadow-md rounded-lg py-10 px-5 mb-10" action=""
            @submit.prevent="validar"
        > <!--el .prevent (modificador de evento) es como en JS e.preventDefault()-->
            <div class="mb-5">
                <label 
                    for="mascota"
                    class="block traxt-gray-700 uppercase font-bold"
                >
                Nombre mascota
            </label>
            <input 
                type="text"
                id="mascota"
                placeholder="Nombre de la mascota"
                class="border-2 w-full p-2 mt-2 placeholder-gray-400 rounded-md focus:border-indigo-500 focus:outline-none"
                :value="nombre"
                @input="$emit('update:nombre', $event.target.value)"
                
            /><!-- v-model es igual a   :value="nombre"
                                        @input="(e) => nombre = e.target.value" -->
            </div>

            <div class="mb-5">
                <label 
                    for="propietario"
                    class="block traxt-gray-700 uppercase font-bold"
                >
                Nombre propietario
            </label>
            <input 
                type="text"
                id="propietario"
                placeholder="Nombre del propietario"
                class="border-2 w-full p-2 mt-2 placeholder-gray-400 rounded-md focus:border-indigo-500 focus:outline-none"
                :value="propietario"
                @input="$emit('update:propietario', $event.target.value)"
            />
            </div>
            <div class="mb-5">
                <label 
                    for="email"
                    class="block traxt-gray-700 uppercase font-bold"
                >
                Email
            </label>
            <input 
                type="email"
                id="email"
                placeholder="Email del propietario"
                class="border-2 w-full p-2 mt-2 placeholder-gray-400 rounded-md focus:border-indigo-500 focus:outline-none"
                :value="email"
                @input="$emit('update:email', $event.target.value)"
            />
            </div>
            <div class="mb-5">
                <label 
                    for="alta"
                    class="block traxt-gray-700 uppercase font-bold"
                >
                Fecha de alta
            </label>
            <input 
                type="date"
                id="alta"
                placeholder="Fecha de alta"
                class="border-2 w-full p-2 mt-2 placeholder-gray-400 rounded-md focus:border-indigo-500 focus:outline-none"
                :value="alta"
                @input="$emit('update:alta', $event.target.value)"
             />
            </div>
            <div class="mb-5">
                <label 
                    for="sintomas"
                    class="block traxt-gray-700 uppercase font-bold"
                >
                Síntomas
            </label>
            <textarea
                id="sintomas"
                placeholder="Describe los síntomas de la mascota"
                class="border-2 w-full p-2 mt-2 placeholder-gray-400 rounded-md focus:border-indigo-500 focus:outline-none h-40"
                :value="sintomas"
                @input="$emit('update:sintomas', $event.target.value)"
            />
            </div>
            <input 
                type="submit"
                class="bg-indigo-600 w-full p-3 uppercase text-white font-bold hover:bg-indigo-700 cursor-pointer transition-colors"
                value="registrar paciente"
            />
            <Alertas
            v-if="alerta.mensaje"
            :alerta="alerta"
        />


        </form>
    </div>
</template>