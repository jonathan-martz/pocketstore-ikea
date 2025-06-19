<template>
  <div class="modal">
    <!-- Put this part before </body> tag -->
    <input
      type="checkbox"
      id="my_modal_8"
      v-model="truckModal"
      class="modal-toggle"
    />
    <div class="modal" role="dialog">
      <div class="modal-box">
        <h3 class="text-lg font-bold">Lieferung aus deiner Nähe</h3>
        <ul class="list bg-base-100 rounded-box shadow-md">
          <li v-for="store in stores" class="list-row">
            <div>
              <img
                class="size-10 rounded-box"
                src="https://place-hold.it/64x64"
              />
            </div>
            <div>
              <div>{{ store.name }}</div>
              <div class="text-sm font-semibold opacity-60">
                {{ store.zip }} - {{ store.city }}
              </div>
            </div>
            <button class="btn btn-square btn-ghost">
              <FontAwesomeIcon :icon="faBox" size="1x" />
            </button>
            <button class="btn btn-square btn-ghost">
              <FontAwesomeIcon :icon="faTruck" size="1x" />
            </button>
          </li>
        </ul>
      </div>
      <label class="modal-backdrop" @click="truckModal = false">Close</label>
    </div>
  </div>
</template>

<script setup lang="ts">
import { useLocalStorage } from "@vueuse/core";
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";
import { faTruck, faBox } from "@fortawesome/free-solid-svg-icons";
import { usePocketBase } from "@/util/pocketbase";

const pb = usePocketBase();
const stores = ref([]);

const truckModal = useLocalStorage("truckModal", false, {});

onMounted(async () => {
  stores.value = await pb.collection("stores").getFullList(10);
});
</script>