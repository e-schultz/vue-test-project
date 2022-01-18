<script setup>
import { ref } from "Vue";
import DynamicOne from "./DynamicOne.vue";
import DynamicTwo from "./DynamicTwo.vue";

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
  </div>
</template>
