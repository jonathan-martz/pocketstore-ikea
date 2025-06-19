<template>
  <div>
    <section class="header bg-black px-3 py-3 mb-3 text-white">
      <div class="hidden md:flex md:justify-between">
        <section class="language flex items-center">
          <FontAwesomeIcon :icon="faFlag" class=""></FontAwesomeIcon>
          <select
            name=""
            id=""
            class="select select-sm bg-transparent select-bordered"
          >
            <option value="">DE - Deutsch</option>
          </select>
        </section>
        <section
          @click="saleModal = true"
          class="sale flex items-center cursor-pointer"
        >
          <button @click="saleModal = true">
            <FontAwesomeIcon :icon="faGift"></FontAwesomeIcon>
            <span class="text-sm ml-3"
              >Sale - Jetzt in deinem IKEA Einrichtungshaus</span
            >
          </button>
        </section>
        <section class="zipcode-and-location space-x-6 flex items-center">
          <button @click="truckModal = true" class="cursor-pointer">
            <FontAwesomeIcon :icon="faTruck"></FontAwesomeIcon>
            <span class="text-sm ml-3">PLZ eingeben</span>
          </button>
          <button @click="locationModal = true" class="cursor-pointer">
            <FontAwesomeIcon :icon="faStore"></FontAwesomeIcon>
            <span class="text-sm ml-3">Standort auswählen</span>
          </button>
        </section>
      </div>
      <section class="logo flex justify-between md:hidden">
        <section class="logo">
          <img
            src="https://www.ikea.com/global/assets/logos/brand/ikea.svg"
            alt=""
            class="h-10"
          />
        </section>
        <nav class="items-center flex">
          <section v-if="!drawer" class="bars">
            <button @click="drawer = !drawer" class="btn btn-primary">
              <FontAwesomeIcon :icon="faBars" />
            </button>
          </section>
          <section v-else class="times">
            <button @click="drawer = !drawer" class="btn btn-primary">
              <FontAwesomeIcon :icon="faTimes" />
            </button>
          </section>
        </nav>
      </section>
    </section>
    <section
      class="hidden header bg-transparent max-w-6xl mx-auto class mb-3 md:flex md:justify-between"
    >
      <div class="flex">
        <img
          src="https://www.ikea.com/global/assets/logos/brand/ikea.svg"
          alt=""
        />
        <label class="input ml-5">
          <FontAwesomeIcon :icon="faMagnifyingGlass" />
          <input type="search" required class="ml-3" placeholder="Search" />
        </label>
      </div>
      <div class="space-x-6 bg-white flex items-center px-3">
        <button>
          <FontAwesomeIcon :icon="faUser"></FontAwesomeIcon>
          <span class="text-sm ml-3">Hej, Jonathan</span>
        </button>
        <button>
          <FontAwesomeIcon
            :icon="faHeart"
            class="text-red-400"
          ></FontAwesomeIcon>
        </button>
        <button>
          <FontAwesomeIcon :icon="faShoppingCart"></FontAwesomeIcon>
        </button>
      </div>
    </section>
    <section class="test px-3 md:hidden">
      <ul class="space-y-3">
        <li class="">
          <button
            @click="saleModal = true"
            class="btn btn-block bg-black text-white"
          >
            <FontAwesomeIcon :icon="faGift"></FontAwesomeIcon>
            <span class="text-sm ml-3">Sale - Gutschein Code</span>
          </button>
        </li>
        <li class="">
          <button
            @click="truckModal = true"
            class="btn btn-block bg-black text-white"
          >
            <FontAwesomeIcon :icon="faTruck"></FontAwesomeIcon>
            <span class="text-sm ml-3">Lieferung auswählen</span>
          </button>
        </li>
        <li class="">
          <button
            @click="locationModal = true"
            class="btn btn-block bg-black text-white"
          >
            <FontAwesomeIcon :icon="faStore"></FontAwesomeIcon>
            <span class="text-sm ml-3">Standort auswählen</span>
          </button>
        </li>
      </ul>
    </section>
    <ModalTruck />
    <ModalLocation />
    <ModalSale />
    <div class="drawer">
      <input
        id="my-drawer"
        type="checkbox"
        v-model="drawer"
        class="drawer-toggle"
      />
      <div class="drawer-side">
        <label
          for="my-drawer"
          aria-label="close sidebar"
          class="drawer-overlay"
        ></label>
        <ul class="menu bg-black text-white min-h-full w-80 p-4">
          <!-- Sidebar content here -->
          <li>
            <img
              src="https://www.ikea.com/global/assets/logos/brand/ikea.svg"
              alt=""
              class="mr-auto"
            />
          </li>
          <li>
            <div class="divider-primary divider">Produkte</div>
          </li>
          <li><a>Bett</a></li>
          <li><a>KleiderSchrank</a></li>
          <li><a>Küche</a></li>
          <li><a>Tisch</a></li>
          <li>
            <div class="divider-primary divider">Räume</div>
          </li>
          <li><a>Schlafzimmer</a></li>
          <li><a>Küche</a></li>
          <li><a>Bad</a></li>
          <li><a>Wohnzimmer</a></li>
          <li>
            <div class="divider-primary divider">Hallo Welt</div>
          </li>
          <li><a>Sidebar Item 1</a></li>
          <li><a>Sidebar Item 2</a></li>
          <li><a>Sidebar Item 2</a></li>
          <li><a>Sidebar Item 2</a></li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";
import {
  faTruck,
  faStore,
  faFlag,
  faUser,
  faMagnifyingGlass,
  faCopy,
  faBars,
  faTimes,
  faHeart,
  faShoppingCart,
  faGift,
} from "@fortawesome/free-solid-svg-icons";

import { useLocalStorage } from "@vueuse/core";

const drawer = useLocalStorage("drawer", false, {});
const saleModal = useLocalStorage("saleModal", false, {});
const truckModal = useLocalStorage("truckModal", false, {});
const locationModal = useLocalStorage("locationModal", false, {});

onMounted(() => {
  drawer.value = false;
  saleModal.value = false;
  truckModal.value = false;
  locationModal.value = false;
});
</script>