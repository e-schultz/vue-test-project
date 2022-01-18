<script setup>
import DynamicOne from "./DynamicOne.vue"
import DynamicTwo from "./DynamicTwo.vue"
let message = "Test";
</script>
<template>
<component :is="DynamicOne"/>
<br/>
<component :is="DynamicTwo"/>
{{message}}
</template>