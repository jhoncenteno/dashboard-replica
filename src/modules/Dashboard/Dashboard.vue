<script setup>
import ChartCard from './ChartCard.vue';

const chartCategories = [
    '01. Sep', '02. Sep', '03. Sep', '04. Sep',
    '05. Sep', '06. Sep', '07. Sep', '08. Sep',
    '09. Sep', '10. Sep', '11. Sep', '12. Sep',
    '13. Sep', '14. Sep'
]

const chartData = [0, 20, 38, 40, 15, 10, 15, 18, 14, 12, 20, 35, 42, 0]

</script>

<template>

    <div class="flex items-start gap-10">

        <div class="w-1/6">
            <div class="bg-white p-4 rounded-lg space-y-4">
                <div class="flex items-center justify-between">
                    <div class="flex items-center gap-2">
                        <span>+</span>
                        <h2 class="text-lg font-semibold">Brand Voices</h2>
                    </div>
                    <button
                        class="bg-indigo-500 text-white rounded-full w-6 h-6 flex items-center justify-center text-sm">
                        +
                    </button>
                </div>

                <ul class="space-y-2 text-gray-700 text-sm">
                    <li>Green Gardens</li>
                    <li>Hustle Plazza</li>
                    <li>John Phelps</li>
                    <li>Quad Adventure</li>
                    <li>Simon Harries</li>
                </ul>
            </div>
        </div>

        <div class="flex-1 space-y-8">
            <div class="flex flex-wrap justify-between items-stretch gap-4">

                <div class="flex flex-wrap gap-4">
                    <select class="bg-white px-4 rounded text-gray-700">
                        <option>All Brand Voices</option>
                    </select>
                    <select class="bg-white px-4 rounded text-gray-700">
                        <option>This Month</option>
                    </select>
                    <select class="bg-white px-4 rounded text-gray-700">
                        <option>All Team Members</option>
                    </select>
                </div>

                <div class="flex gap-8">
                    <div class="flex flex-col text-center">
                        <span class="text-lg font-bold text-gray-800">512</span>
                        <span class="text-xs text-gray-500">Total Comments</span>
                    </div>
                    <div class="flex flex-col text-center">
                        <p class="text-lg font-bold text-gray-800">432</p>
                        <p class="text-xs text-gray-500">Total Actions</p>
                    </div>
                </div>

            </div>

            <ChartCard title="Comments" :data="chartData" :categories="chartCategories" />
            <ChartCard title="Actions" :data="chartData" :categories="chartCategories" />

        </div>

    </div>

</template>

<style scoped></style>
