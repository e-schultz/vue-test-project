<script setup>
const props = defineProps({
  label: String,
  placeholder: String,
  name: String,
});
</script>
<template>
  <label>{{ label }}</label>
  <input type="text" :name="name" :placeholder="placeholder" />
</template>
