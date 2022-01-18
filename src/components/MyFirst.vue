<script setup>
import { ref } from "Vue"
import DynamicOne from "./DynamicOne.vue"
import DynamicTwo from "./DynamicTwo.vue"
let message = "Test";
let showWich = ref("DynamicOne")
</script>
<template>

Showing .... {{showWich}}
<component :is="showWich"/>
<button @click="showWich = (showWich == 'DynamicOne') ? 'DynamicTwo' : 'DynamicOne'">Swap</button>
</template>