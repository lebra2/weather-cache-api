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
                <div class="bg-white overflow-hidden shadow-sm sm:rounded-lg">
                    <h1>Weather app</h1>
                </div>
            </div>
            <div class="flex flex-col justify-center items-center">
                <h2>{{ props.data.name }}</h2>
                <img :src="`https://openweathermap.org/img/wn/${props.data.weather[0].icon}.png`" alt="">
                <h2>Kraadi {{ props.data.main.temp }}</h2>
                <h2>Tundub nagu {{ props.data.main.feels_like }}</h2>
                <h2>{{ props.data.name }}</h2>
            </div>

        </div>
    </AuthenticatedLayout>
</template>
