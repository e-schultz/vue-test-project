<template>
  <div>
    <h1>Data Binding</h1>
    <component
      v-for="(field, index) in schema"
      :key="index"
      :is="field.fieldType"
      v-model="formData[field.name]"
      v-bind="field"
    >
    </component>
    <p>
      Hello {{ formData.title }} {{ formData.firstName }} {{ formData.lastName }}, I hear
      you are {{ formData.age }} years old.
    </p>
  </div>
</template>

<script>
import NumberInput from "../components/BlogPort/NumberInput.vue";
import SelectList from "../components/BlogPort/SelectList.vue";
import TextInput from "../components/BlogPort/TextInput.vue";

export default {
  name: "FormsDemo",
  components: { NumberInput, SelectList, TextInput },
  data() {
    return {
      formData: {
        firstName: "Evan",
        lastName: "Schultz",
        age: 38,
      },
      schema: [
        {
          fieldType: "SelectList",
          name: "title",
          multi: false,
          label: "Title",
          options: ["", "Mr", "Ms", "Mx", "Dr", "Madam", "Lord"],
        },
        {
          fieldType: "TextInput",
          placeholder: "First Name",
          label: "First Name",
          name: "firstName",
        },
        {
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
        },
      ],
    };
  },
};
</script>
