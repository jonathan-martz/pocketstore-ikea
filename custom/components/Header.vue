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
            <button onclick="modal_gift.showModal()">
                <Fa :icon="faGift" class="mr-2" />
                <span>50 Jahre IKEA Deutschland</span>
            </button>
        </section>
        <dialog id="modal_gift" class="modal">
            <div class="modal-box text-black">
                <h3 class="text-lg font-bold">Hello!</h3>
                <p class="py-4">Press ESC key or click outside to close</p>
            </div>
            <form method="dialog" class="modal-backdrop">
                <button>close</button>
            </form>
        </dialog>
        <section class="store-select flex items-center">

            <button onclick="modal_delivery.showModal()"
                class="btn border-none hover:bg-transparent hover:border-none text-white bg-black">
                <Fa :icon="faTruck" class="mr-2" />
                <span>PLZ
                    eingeben</span>
            </button>
            <dialog id="modal_delivery" class="modal">
                <div class="modal-box text-black">
                    <h3 class="text-lg font-bold">Hello!</h3>
                    <p class="py-4">Press ESC key or click outside to close</p>
                </div>
                <form method="dialog" class="modal-backdrop">
                    <button>close</button>
                </form>
            </dialog>
            <span class="px-3 py-3">|</span>
            <button onclick="modal_location.showModal()"
                class="btn border-none hover:bg-transparent hover:border-none text-white bg-black">
                <Fa :icon="faHouse" class="mr-2" />
                <span>Standort auswählen</span>
            </button>
            <dialog id="modal_location" class="modal">
                <div class="modal-box text-black">
                    <h3 class="text-lg font-bold">Hello!</h3>
                    <p class="py-4">Press ESC key or click outside to close</p>
                </div>
                <form method="dialog" class="modal-backdrop">
                    <button>close</button>
                </form>
            </dialog>
        </section>
    </div>
    <div class="w-full bg-white mb-3 px-3 py-3 justify-between max-w-6xl mx-auto hidden md:flex">
        <section class="logo-search flex">
            <a href="/">
                <img src="https://www.ikea.com/global/assets/logos/brand/ikea.svg" class="h-8" alt="">
            </a>
            <div class="flex ml-3 bg-gray-400">
                <div class="px-3 flex items-center">
                    <a href="/search">
                        <Fa :icon="faMagnifyingGlass" />
                    </a>
                </div>
            </div>
            <ul class="flex space-x-6 items-center ml-3 text-sm font-bold">
                <li><a href="/de/produkte.html">Produkte</a></li>
                <li><a href="/de/räume.html">Räume</a></li>
                <li><button onclick="modal_location.showModal()">Standort</button></li>
                <li><button onclick="modal_delivery.showModal()">Lieferung</button></li>
                <li><a href="/customer/profile">Kundenkonto</a></li>
            </ul>
        </section>
        <section class="icons flex justify-end space-x-6 bg-gray-400 px-3">
            <section class="icon mt-1 mr-2">
                <Fa :icon="faHeart" />
            </section>
            <section class="icon mt-1 mr-2">
                <Fa :icon="faShoppingCart" />
            </section>
        </section>
    </div>
    <section class="header md:hidden flex justify-between px-3 py-3 bg-black mb-2">
        <section class="logo">
            <a href="/">
                <img src="https://www.ikea.com/global/assets/logos/brand/ikea.svg" class="h-8" alt="">
            </a>
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
    <MobileContent />
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