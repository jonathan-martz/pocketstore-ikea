<template>
    <div class="w-full bg-black px-3 py-3 text-white flex justify-between md:flex hidden">
        <section class="lang-select flex items-center">
            <section class="icon mx-3">
                <Fa :icon="faGlobe" />
            </section>
            <select name="" id="" class="select select-xs bg-black text-white">
                <option value="de">DE - Deutsch</option>
            </select>
        </section>
        <section class="features text-sm items-center hidden md:flex">
            <section class="icon mt-1 mx-3">
                <Fa :icon="faGift" />
            </section>
            <span>50 Jahre IKEA Deutschland</span>
        </section>
        <section class="store-select flex items-center">
            <section class="icon mt-1 mx-3">
                <Fa :icon="faTruck" />
            </section>
            <button class="btn border-none hover:bg-transparent hover:border-none text-white bg-black">PLZ
                eingeben</button>
            <span class="px-3 py-3">|</span>
            <section class="icon mt-1 mx-3">
                <Fa :icon="faHouse" />
            </section>
            <button class="btn border-none hover:bg-transparent hover:border-none text-white bg-black">Standort
                auswählen</button>
        </section>
    </div>
    <div class="w-full bg-white mb-3 px-3 py-3 justify-between max-w-6xl mx-auto hidden md:flex">
        <section class="logo-search flex">
            <img src="https://www.ikea.com/global/assets/logos/brand/ikea.svg" class="h-8" alt="">
            <div class="flex ml-3 bg-gray-400">
                <div class="px-3 flex items-center">
                    <Fa :icon="faMagnifyingGlass" />
                </div>
            </div>
        </section>
        <section class="icons flex justify-end space-x-6 bg-gray-400 px-3">
            <section class="icon mt-1">
                <Fa :icon="faUser" />
            </section>
            <section class="icon mt-1 mr-2">
                <Fa :icon="faHeart" />
            </section>
            <section class="icon mt-1 mr-2">
                <Fa :icon="faShoppingCart" />
            </section>
            <nav>
                <section v-if="!open" class="bars">
                    <button @click="open = !open" type="button">
                        <FontAwesomeIcon color="black" size="1x" class="w-5 mt-2 mr-2" :icon="faBars" />
                    </button>
                </section>
                <section v-else class="times">
                    <button @click="open = !open" type="button">
                        <FontAwesomeIcon color="black" size="1x" class="w-5 mt-2 mr-2" :icon="faTimes" />
                    </button>
                </section>
            </nav>
        </section>
    </div>
    <section class="header md:hidden flex justify-between px-3 py-3 bg-black mb-2">
        <section class="logo">
            <img src="https://www.ikea.com/global/assets/logos/brand/ikea.svg" class="h-8" alt="">
        </section>
        <section v-if="!open" class="bars">
            <button @click="open = !open" type="button">
                <FontAwesomeIcon color="white" size="2x" class="w-5 mr-2" :icon="faBars" />
            </button>
        </section>
        <section v-else class="times">
            <button @click="open = !open" type="button">
                <FontAwesomeIcon color="white" size="2x" class="w-5 mr-2" :icon="faTimes" />
            </button>
        </section>
    </section>
    <section v-if="open" class="header-content md:hidden grid grid-cols-6 gap-3 px-3 mb-2">
        <div class="col-span-3">
            <a href="/" class="btn btn-warning btn-block btn-sm">
                Startseite
            </a>
        </div>
        <div class="col-span-3">
            <a href="/search" class="btn btn-warning btn-block btn-sm">
                Suche
            </a>
        </div>
        <div class="col-span-3">
            <a href="/profile" class="btn btn-warning btn-block btn-sm">
                Profile
            </a>
        </div>
        <div class="col-span-3">
            <a href="/impressum" class="btn btn-warning btn-block btn-sm">
                Impressum
            </a>
        </div>
    </section>
</template>
<script setup lang="ts">
import { faBars, faTimes, faGift, faGlobe, faHeart, faHouse, faMagnifyingGlass, faShoppingCart, faTruck, faUser } from '@fortawesome/free-solid-svg-icons';
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome';
import { useLocalStorage } from '@vueuse/core';

const open = useLocalStorage('open-mobile', false, {});

onMounted(() => {
    open.value = false;
})
</script>