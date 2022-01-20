<script setup>
import { ref, computed } from "vue";
import DynamicOne from "./DynamicOne.vue";
import DynamicTwo from "./DynamicTwo.vue";
import TextInput from "./TextInput.vue";
let message = "Test";
let schema = [
  /*{
    fieldType: "SelectList",
    name: "title",
    multi: false,
    label: "Title",
    options: ["Ms", "Mr", "Mx", "Dr", "Madam", "Lord"],
  },*/
  {
    fieldType: "TextInput",
    placeholder: "First Name",
    label: "First Name",
    name: "firstName",
  },
  /*{
    fieldType: "TextInput",
    placeholder: "Last Name",
    label: "Last Name",
    name: "lastName",
  },
  {
    fieldType: "NumberInput",
    placeholder: "Age",
    name: "age",
    label: "Age",
    minValue: 0,
  },*/
];
let showWich = ref("DynamicOne");
let firstName = ref("Evan");
let lastName = ref("Schultz");
let fullName = computed(() => `${firstName} ${lastName.value}`);
</script>
<template>
  <div>
    Showing .... {{ showWich }}
    <component :is="showWich" />
    <button @click="showWich = showWich == 'DynamicOne' ? 'DynamicTwo' : 'DynamicOne'">
      Swap
    </button>
    <br />
    <component :is="TextInput" v-bind="schema[0]" />
    <br />
    Hey {{ firstName }} {{ lastName }} <br />
    {{ fullName }}
  </div>
</template>
