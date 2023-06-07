<template>
    <div class="box has-text-weight-bold boxLista">
        <slot></slot>
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
export default defineComponent({
    name: 'BoxLista'
})
</script>

<style>
.boxLista {
    background: #FAF0CA;
    /* color: var(--texto-primario); */
}
</style>
