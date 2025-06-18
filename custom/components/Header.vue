<template>
  <div>
    <section class="header bg-black px-3 py-3 mb-3 text-white">
      <div class="flex justify-between">
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
    </section>
    <section
      class="header bg-transparent max-w-6xl mx-auto class mb-3 flex justify-between"
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
          <FontAwesomeIcon :icon="faHeart" class="text-red-400"></FontAwesomeIcon>
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
  faHeart,
  faShoppingCart,
  faGift,
} from "@fortawesome/free-solid-svg-icons";
</script>