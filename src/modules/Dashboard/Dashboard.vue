<script setup>
import ChartCard from './ChartCard.vue';

const totalComments = 512
const totalActions = 432
const brandVoices = [
    "Green Gardens",
    "Hustle Plazza",
    "John Phelps",
    "Quad Adventure",
    "Simon Harries",
]

// Chart Values
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
                    <button class="bgMain text-white rounded w-6 h-6 flex items-center justify-center text-lg">
                        +
                    </button>
                </div>

                <ul class="space-y-2 text-gray-700 text-sm">
                    <li v-for="(voice, index) in brandVoices" :key="index">{{ voice }}</li>
                </ul>
            </div>
        </div>

        <div class="flex-1 space-y-8">
            <div class="flex flex-wrap justify-between items-stretch gap-4">

                <div class="flex flex-wrap gap-4">

                    <div class="relative">
                        <select class="text-gray-700 font-bold">
                            <option>All Brand Voices</option>
                        </select>
                        <img src="../../assets/icons/arrow-down.svg" alt="Arrow Down"
                            class="absolute right-3 top-1/2 -translate-y-1/2 w-4 h-4" />
                    </div>

                    <div class="relative">
                        <select class="text-gray-700 font-bold">
                            <option>This Month</option>
                        </select>
                        <img src="../../assets/icons/arrow-down.svg" alt="Arrow Down"
                            class="absolute right-3 top-1/2 -translate-y-1/2 w-4 h-4" />
                    </div>

                    <div class="relative">
                        <select class="text-gray-700 font-bold">
                            <option>All Team Members</option>
                        </select>
                        <img src="../../assets/icons/arrow-down.svg" alt="Arrow Down"
                            class="absolute right-3 top-1/2 -translate-y-1/2 w-4 h-4" />
                    </div>

                </div>

                <div class="flex gap-8">
                    <div class="flex flex-col text-center">
                        <span class="text-lg font-bold text-gray-800">{{ totalComments }}</span>
                        <span class="text-xs text-main font-semibold">Total Comments</span>
                    </div>
                    <div class="flex flex-col text-center">
                        <p class="text-lg font-bold text-gray-800">{{ totalActions }}</p>
                        <p class="text-xs text-main font-semibold">Total Actions</p>
                    </div>
                </div>

            </div>

            <ChartCard title="Comments" :data="chartData" :categories="chartCategories" />
            <ChartCard title="Actions" :data="chartData" :categories="chartCategories" />

        </div>

    </div>

</template>

<style scoped>
select {
    height: 100%;
    appearance: none;
    background-color: white;
    padding-left: 1rem;
    padding-right: 2.5rem;
    border-radius: .25rem;
}
</style>
