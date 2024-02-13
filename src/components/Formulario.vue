<script setup>

</script>

<template>
    <div class="md:w-1/2">
        <h2 class="font-black text-3xl text-center">Seguimiento pacientes</h2>
        <p class="text-lg mt-5 text-center mb-10">
            Añade pacientes y
            <span class="text-indigo-600 font-bold">adminístralos</span>
        </p>

        <form class="bg-white shadow-md rounded-lg py-10 px-5 mb-10" action="">
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
            />
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
            
            />
            </div>



        </form>
    </div>
</template>