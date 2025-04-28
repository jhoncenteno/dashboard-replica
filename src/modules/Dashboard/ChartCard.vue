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

const chartColor = '#1E40AF';
const gridColor = '#f3f4f6';
const chartWidth = 3

const options = {
    chart: {
        height: "100%",
        type: 'line',
        zoom: {enabled: false},
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
        align: 'left'
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
            offsetX: 0,
            offsetY: 0
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
            formatter: function (val) {
                const allowed = [5, 10, 20, 30, 40, 50];
                return allowed.includes(val) ? val : '';
            }
        }
    },
    tooltip: {
        marker: { show: false },
        y: {
            title: {
                formatter: () => ''
            },
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

    <div class="w-full h-[260px] p-2 bg-white rounded">
        <VueApexCharts width="100%" height="100%" type="line" :options="options" :series="series" />
    </div>
</template>

<style scoped></style>
