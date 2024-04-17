<script setup>
import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
import { Head } from '@inertiajs/vue3';

const props = defineProps({
    data: Object
})

console.log(props.data)

</script>


<template>
    <Head title="Dashboard" />

    <AuthenticatedLayout>
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">Dashboard</h2>
        </template>

        <div class="py-12">
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <div class=" overflow-hidden shadow-sm sm:rounded-lg">
                    <h1 class="text-2xl">Weather app</h1>
                </div>
            </div>
            <div class="flex flex-col justify-center items-center mt-12 ">
                <div class="flex flex-col items-center bg-slate-300 rounded-lg p-16">
                    <h2 class="text-2xl">{{ props.data.name }}</h2>
                    <img class="w-24 h-24" :src="`https://openweathermap.org/img/wn/${props.data.weather[0].icon}.png`" alt="">
                    <h2 class=text-xl>{{ props.data.main.temp }} °</h2>
                    <h2 class="text-xl">Tundub nagu {{ props.data.main.feels_like }}</h2>
                </div>

            </div>

        </div>
    </AuthenticatedLayout>
</template>
