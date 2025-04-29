<script setup>
import ChartCard from './ChartCard.vue';
import arrowDown from '../../assets/icons/arrow-down.svg'
import speaker from '../../assets/icons/speaker.svg'
import plus from '../../assets/icons/plus.svg'
import { ref } from 'vue';

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

const showNewVoiceTooltip = ref(false)

</script>

<template>

    <div class="flex items-start gap-10 h-full">

        <div class="w-[12vw]">
            <div class="bg-white p-4 rounded-lg space-y-4 transform transition-transform hover:scale-105">
                <div class="flex items-center justify-between">
                    <div class="flex items-center gap-2">
                        <img :src="speaker" alt="Speaker" class="w-3" />
                        <h2 class="text-base font-bold">Brand Voices</h2>
                    </div>
                    <div class="relative" @mouseenter="showNewVoiceTooltip = true"
                        @mouseleave="showNewVoiceTooltip = false">
                        <button class="bgMain rounded p-1 flex items-center justify-center cursor-pointer">
                            <img :src="plus" alt="Add" class="w-3 invert" />
                        </button>
                        <div v-show="showNewVoiceTooltip"
                            class="absolute left-1/2 -translate-x-1/2 mt-2 w-30 bg-white px-2 py-1 rounded shadow z-10">
                            <p class="text-xs font-semibold text-center">You can add new brand voices here!</p>
                        </div>
                    </div>
                </div>

                <ul class="space-y-2 text-gray-700 text-sm">
                    <li v-for="(voice, index) in brandVoices" :key="index">{{ voice }}</li>
                </ul>
            </div>
        </div>

        <div class="h-full flex-1 flex flex-col justify-between">
            <div class="flex flex-wrap justify-between items-stretch gap-4">

                <div class="flex flex-wrap gap-4">

                    <div class="relative transform transition-transform hover:scale-105">
                        <select class="text-gray-700 font-bold">
                            <option>All Brand Voices</option>
                        </select>
                        <img :src="arrowDown" alt="Arrow Down"
                            class="absolute right-3 top-1/2 -translate-y-1/2 w-4 h-4" />
                    </div>

                    <div class="relative transform transition-transform hover:scale-105">
                        <select class="text-gray-700 font-bold">
                            <option>This Month</option>
                        </select>
                        <img :src="arrowDown" alt="Arrow Down"
                            class="absolute right-3 top-1/2 -translate-y-1/2 w-4 h-4" />
                    </div>

                    <div class="relative transform transition-transform hover:scale-105">
                        <select class="text-gray-700 font-bold">
                            <option>All Team Members</option>
                        </select>
                        <img :src="arrowDown" alt="Arrow Down"
                            class="absolute right-3 top-1/2 -translate-y-1/2 w-4 h-4" />
                    </div>

                </div>

                <div class="flex gap-8">
                    <div class="flex flex-col text-center">
                        <span class="text-lg font-bold text-gray-800">{{ totalComments }}</span>
                        <span class="text-xs text-main-color font-semibold">Total Comments</span>
                    </div>
                    <div class="flex flex-col text-center">
                        <p class="text-lg font-bold text-gray-800">{{ totalActions }}</p>
                        <p class="text-xs text-main-color font-semibold">Total Actions</p>
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
