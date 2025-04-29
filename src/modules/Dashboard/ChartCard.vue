<script setup>
import VueApexCharts from 'vue3-apexcharts';

const props = defineProps({
    title: {
        type: String,
        required: true
    },
    categories: {
        type: Array,
        required: true
    },
    data: {
        type: Array,
        required: true
    }
})

const chartColor = 'var(--main-bg)';
const gridColor = '#f3f4f6';
const chartWidth = 3

const options = {
    chart: {
        height: "100%",
        type: 'line',
        zoom: { enabled: false },
        toolbar: { show: false },
        background: '#ffffff',
    },
    colors: [chartColor],
    dataLabels: {
        enabled: false
    },
    stroke: {
        curve: "smooth",
        width: chartWidth
    },
    title: {
        text: props.title,
        align: 'left',
        style: {
            fontSize: '16px',
        }
    },
    grid: {
        borderColor: gridColor,
        row: {
            colors: ['transparent'],
            opacity: 0.1
        },
        padding: {
            left: 20
        }
    },
    xaxis: {
        categories: props.categories,
        tooltip: { enabled: false },
        axisBorder: {
            show: true,
            color: chartColor,
            height: chartWidth,
            width: '100%',
        },
    },
    markers: {
        colors: ['#FFFFFF'],
        strokeColor: chartColor,
        strokeWidth: 3,
    },
    yaxis: {
        min: 0,
        max: 50,
        tickAmount: 5,
        labels: {
            // Hide label for 0 value
            formatter: function (val) {
                return val !== 0 ? val : '';
            }
        }
    },
    tooltip: {
        marker: { show: false },
        y: {
            title: {
                // Hide title value
                formatter: () => ''
            },
            // Style tooltip text
            formatter: function (val) {
                return `<div style="text-align: center;">${val}<br/>${props.title}</div>`
            }
        },
        x: { show: false }
    },

}

const series = [{
    name: props.title,
    data: props.data
}]


</script>

<template>
    <div class="w-full aspect-[4.3/1] p-2 bg-white rounded-lg transform transition-transform hover:scale-102">
        <VueApexCharts width="100%" height="100%" type="line" :options="options" :series="series" />
    </div>
</template>

<style scoped></style>
