<template>
  <div class="row">
    <div class="col s12 m6">
      <div class="card">
        <div class="card-image">
          <!-- This is the image and the name of the student. -->
          <img src="../assets/girlMin.png" />
          <span class="card-title">{{ name }}</span>
          <!-- A button that calls the deleteSchueler() method when clicked. -->
          <a
            class="btn-floating halfway-fab waves-effect waves-light red"
            @click="deleteSchueler()"
            ><i class="material-icons">delete</i></a
          >
        </div>
        <!-- Displaying the age and telNumber of the student. -->
        <div class="card-content">
          <p>Alter: {{ age }}</p>
          <p>Telefonnummer: {{ telNumber }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "@vue/runtime-core";
export default defineComponent({
  props: {
    // Defining the props that the component will receive from the parent component.
    id: Number,
    name: String,
    age: Number,
    telNumber: String,
  },
  methods: {
    // Emitting an event called deleteStudent and passing the id of the student to the parent
    // component.
    deleteSchueler() {
      this.$emit("deleteStudent", this.id);
      console.log("selected student " + this.id);
    },
  },
});
</script>