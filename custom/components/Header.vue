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
        <section class="sale flex items-center">
          <FontAwesomeIcon :icon="faGift"></FontAwesomeIcon>
          <span class="text-sm ml-3"
            >Sale - Jetzt in deinem IKEA Einrichtungshaus</span
          >
        </section>
        <section class="zipcode-and-location space-x-6 flex items-center">
          <button>
            <FontAwesomeIcon :icon="faTruck"></FontAwesomeIcon>
            <span class="text-sm ml-3">PLZ eingeben</span>
          </button>
          <button>
            <FontAwesomeIcon :icon="faStore"></FontAwesomeIcon>
            <span class="text-sm ml-3">Standort auswählen</span>
          </button>
        </section>
      </div>
      <section class="logo flex justify-between md:hidden">
        <section class="logo">
          <img
            src="https://www.ikea.com/global/assets/logos/brand/ikea.svg"
            alt="" class="h-10 my-3 mx-3"
          />
        </section>
        <nav class="items-center flex">
          <section v-if="!open" class="bars">
            <button @click="open = !open" class="btn btn-primary">
              <FontAwesomeIcon :icon="faBars" />
            </button>
          </section>
          <section v-else class="times">
            <button @click="open = !open" class="btn btn-primary">
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
  faBars,
  faTimes,
  faHeart,
  faShoppingCart,
  faGift,
} from "@fortawesome/free-solid-svg-icons";

import { useLocalStorage } from "@vueuse/core";

const open = useLocalStorage("open", false, {});
</script>