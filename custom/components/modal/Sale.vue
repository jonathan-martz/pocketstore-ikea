<template>
  <div>
    <!-- Put this part before </body> tag -->
    <input type="checkbox" v-model="saleModal" class="modal-toggle" />
    <div class="modal" role="dialog">
      <div class="modal-box">
        <h3 class="text-lg font-bold">
          Sale - Jetzt in deinem IKEA Einrichtungshaus
        </h3>
        <p class="py-4">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Reiciendis
          ducimus culpa nobis, obcaecati ut aperiam esse error rerum. Modi
          minima cupiditate distinctio consectetur at velit placeat illo a id
          tempore?
        </p>
        <label class="input input-bordered input-secondary w-full text-black">
          Ihr Gutschein Code
          <input
            type="text"
            readonly
            placeholder="SALES-Summer"
            class="input text-black input-bordered input-secondary"
          />
          <button
            @click="navigator.clipboard.writeText('SALES-Summer')"
            class="badge badge-secondary"
          >
            <FontAwesomeIcon :icon="faCopy" />
          </button>
        </label>
      </div>
      <label class="modal-backdrop" @click="saleModal = false">Close</label>
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

const saleModal = useLocalStorage("saleModal", false, {});
</script>