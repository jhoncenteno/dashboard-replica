<script setup>
import VueApexCharts from 'vue3-apexcharts';

    const title = "Comments"  
    const options = {
        chart: {
            height: 350,
            type: 'line',
            zoom: {
            enabled: false
            }
        },
        dataLabels: {
            enabled: false
        },
        stroke: {
            curve: "smooth"
        },
        title: {
            text: title,
            align: 'left'
        },
        grid: {
            row: {
            colors: ['#f3f3f3', 'transparent'],
            opacity: 0.5
            },
        },
        xaxis: {
            categories: ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep'],
        }
    }

    const series = [{
        name: "Desktops",
        data: [10, 41, 35, 51, 49, 62, 69, 91, 148]
    }]


</script>

<template>

    <!-- <div class="bg-white rounded-lg p-6 h-62 flex items-center justify-center">
        <span class="text-gray-400">[ Chart ]</span>
    </div> -->

    <div>
        <VueApexCharts width="600" heigth="300" type="line" :options="options" :series="series"/>
    </div>
</template>

<style scoped></style>
