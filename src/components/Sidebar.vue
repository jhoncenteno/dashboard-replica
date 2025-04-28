<script setup>
const items = [
    { name: 'Dashboard' },
    { name: 'Actions' },
    { name: 'Comments' },
    { name: 'Favorites' },
    { name: 'Auto Comment' }
]
</script>

<template>

    <div class="w-64 h-screen bg-white text-black flex flex-col">
        <span class="px-6 py-4 font-bold text-2xl border-gray-700">
            My App
        </span>
        <div class="flex-1 flex flex-col mt-8">
            <ul class="">
                <li v-for="(item, index) in items" :key="index">
                    <span class="block px-8 py-3 w-full" :class="{
                        'bg-purple-600 text-white': index === 0,
                        'hover:bg-purple-600 hover:text-white': index !== 0
                    }">
                        {{ item.name }}
                    </span>
                </li>
            </ul>
            <ul class="mt-auto border-t border-gray-300">
                <li>
                    <span class="block px-8 py-3 hover:bg-purple-500 hover:text-white">Settings</span>
                </li>
            </ul>
        </div>
    </div>
</template>

<style scoped></style>
