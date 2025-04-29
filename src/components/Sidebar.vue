<script setup>
import home from '../assets/icons/home.svg'
import magicWand from '../assets/icons/magic-wand.svg'
import comments from '../assets/icons/comments.svg'
import favorite from '../assets/icons/favorite.svg'
import autoPlay from '../assets/icons/auto-play.svg'
import settingsIcon from '../assets/icons/settings.svg'

const items = [
    { name: 'Dashboard', icon: home },
    { name: 'Actions', icon: magicWand },
    { name: 'Comments', icon: comments },
    { name: 'Favorites', icon: favorite },
    { name: 'Auto Comment', icon: autoPlay }
]

const settings = {
    name: 'Settings', icon: settingsIcon
}
</script>

<template>

    <div class="w-[15vw] h-screen bg-white text-black flex flex-col">
        <span class="px-6 py-4 font-bold text-2xl border-gray-700">
            Dashboard App
        </span>
        <div class="flex-1 flex flex-col mt-8">
            <ul class="">
                <li v-for="(item, index) in items" :key="index">
                    <span class="flex items-center gap-2 px-8 py-3 w-full font-semibold group" :class="{
                        'bgMain text-white': index === 0,
                        'hover:bgMain hover:text-white': index !== 0
                    }">
                        <img :src="item.icon" alt="" class="w-6 group-hover:invert" :class="{ 'invert': index === 0 }">
                        {{ item.name }}
                    </span>
                </li>
            </ul>
            <ul class="mt-auto border-t border-gray-300">
                <li>
                    <span class="flex items-center gap-2 px-8 py-3 hover:bgMain hover:text-white font-semibold group">
                        <img :src="settings.icon" alt="" class="w-5 group-hover:invert">
                        {{ settings.name }}
                    </span>
                </li>
            </ul>
        </div>
    </div>
</template>

<style scoped></style>
