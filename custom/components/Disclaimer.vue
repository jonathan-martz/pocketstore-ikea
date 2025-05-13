<script setup lang="ts">
import { faInfoCircle } from '@fortawesome/free-solid-svg-icons';
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome';
</script>

<template>
    <section class="alert alert-error">
        <FontAwesomeIcon :icon="faInfoCircle" />
        <p class="text-sm text-white">Dies ist ein Demo Store von PocketStore.io</p>
        <FontAwesomeIcon :icon="faInfoCircle" />
    </section>
</template>