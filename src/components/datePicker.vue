<template>
    <h1>date picker</h1>
    <datepicker
      class="picker"
      v-model="selected"
      :locale="locale"
      :upperLimit="to"
      :lowerLimit="from"
      inputFormat="dd.MM.yyyy"
    />
  </template>
  
  <script>
  import DatePicker from "vue3-datepicker";
  import "vue3-datepicker/dist/vue3-datepicker.css";
  import { defineComponent } from "vue";
  import { en } from "date-fns/locale";
  
  export default defineComponent({
    name: "App",
    components: {
      datepicker: DatePicker,
    },
    data() {
      return {
        selected: new Date(),
        from: new Date(),
        to: null,
      };
    },
    computed: {
      locale: () => en,
    },
  });
  </script>
  
  <style>
  </style>