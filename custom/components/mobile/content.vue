<template>
   <section v-if="open" class="header-content md:hidden grid grid-cols-6 gap-3 px-3 mb-2">
        <div class="col-span-6">
            <form action="/search" method="GET">
                <input type="text" name="query" placeholder="Wonach suchst du ?" class="input input-warning w-full text-center">
            </form>
        </div>
        <div class="col-span-3">
            <a href="/de/produkte.html" class="btn btn-warning btn-block btn-sm">
                Produkte
            </a>
        </div>
        <div class="col-span-3">
            <a href="/de/räume.html" class="btn btn-warning btn-block btn-sm">
                Räume
            </a>
        </div>
        <div class="col-span-3">
            <button onclick="modal_location.showModal()" class="btn btn-warning btn-block btn-sm">
                Standorte
            </button>
        </div>
        <div class="col-span-3">
            <button onclick="modal_delivery.showModal()" class="btn btn-warning btn-block btn-sm">
                Lieferung
            </button>
        </div>
        <div class="col-span-3">
            <a href="/de/profile" class="btn btn-warning btn-block btn-sm">
                Profile
            </a>
        </div>
        <div class="col-span-3">
            <a href="/customer/logout" class="btn btn-warning btn-block btn-sm">
                Logout
            </a>
        </div>
    </section>
</template>

<script setup lang="ts">
import { useLocalStorage } from '@vueuse/core';

const open = useLocalStorage('open-mobile', false, {});

onMounted(() => {
    open.value = false;
})
</script>