<template>
  <div>
    <label>{{ label }}</label>

    <input
      type="text"
      :name="name"
      :value="modelValue"
      :placeholder="placeholder"
      @input="$emit('update:modelValue', $event.target.value)"
    />
  </div>
</template>
<script>
export default {
  name: "TextInput",
  props: ["placeholder", "label", "name", "modelValue", "fieldType"],
};
// https://v3.vuejs.org/guide/component-basics.html#using-v-model-on-components
</script>
