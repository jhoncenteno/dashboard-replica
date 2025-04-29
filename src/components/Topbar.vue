<script setup>
import { ref } from 'vue'
import creditCard from '../assets/icons/credit-card.svg'
import bell from '../assets/icons/bell.svg'
import user from '../assets/images/user.jpg'
import arrowDown from '../assets/icons/arrow-down.svg'

const credits = 30
const showNotificationsTooltip = ref(false)
</script>

<template>
    <div class="flex justify-between w-full h-13 bg-white items-center px-8">
        <h1 class="text-xl font-semibold text-black">Dashboard</h1>
        <div class="flex items-center gap-4">
            <div
                class="flex items-center gap-1 bg-gray-100 rounded-lg py-1 px-3 border border-gray-200 transform transition-transform hover:scale-105">
                <img :src="creditCard" alt="Credit card" class="w-5">
                <span class="text-xs font-bold text-gray-600">{{ credits }} credits</span>
            </div>
            <div class="relative" @mouseenter="showNotificationsTooltip = true"
                @mouseleave="showNotificationsTooltip = false">
                <img :src="bell" alt="Bell" role="button" class="w-5 cursor-pointer transform transition-transform hover:scale-110">
                <div v-show="showNotificationsTooltip"
                    class="absolute left-1/2 -translate-x-1/2 mt-2 w-28 bg-white px-2 py-1 rounded shadow z-10">
                    <p class="text-xs font-semibold text-center">There are no new notifications</p>
                </div>
            </div>
            <div class="flex items-center gap-1 pl-4 border-l border-gray-200 cursor-pointer">
                <img :src="user" alt="User" class="w-5 rounded-full">
                <img :src="arrowDown" alt="Arrow down" class="w-4 rounded-full">
            </div>
        </div>
    </div>
</template>

<style scoped></style>
