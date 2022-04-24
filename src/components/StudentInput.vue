<template>
  <div class="row">
    <form class="col s12">
      <div class="row"><h1>Enter a new Student 🤩</h1></div>
      <div class="row">
        <div class="input-field col s6">
          <i class="material-icons prefix">account_circle</i>
          <input
            id="firstname"
            type="text"
            class="validate"
            v-model="firstname"
          />
          <label for="firstname">First Name</label>
        </div>
        <div class="input-field col s6">
          <i class="material-icons prefix">account_box</i>
          <input
            id="lastname"
            type="text"
            class="validate"
            v-model="lastname"
          />
          <label for="lastname">Last Name</label>
        </div>
      </div>
      <div class="row">
        <div class="input-field col s6">
          <i class="material-icons prefix">cake</i>
          <input id="age" type="number" class="validate" v-model="age" />
          <label for="age">Age</label>
        </div>
        <div class="input-field col s6">
          <i class="material-icons prefix">phone</i>
          <input
            id="telNumber"
            type="tel"
            class="validate"
            v-model="telNumber"
          />
          <label for="telNumber">Telephone</label>
        </div>
      </div>
    </form>
    <div class="row">
      <a class="waves-effect waves-light btn" @click="addSchueler"
        ><i class="material-icons right">add_circle_outline</i>add</a
      >
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "@vue/runtime-core";
export default defineComponent({
  data() {
    return {
      firstname: "",
      lastname: "",
      age: "",
      telNumber: "",
    };
  },
  methods: {
    // A method that is called when the user clicks the add button. It creates a new student object and
    // emits an event called addStudent.
    addSchueler() {
      let student = {
        firstname: this.firstname,
        lastname: this.lastname,
        age: parseInt(this.age),
        telNumber: this.telNumber,
      };
      this.$emit("addStudent", student);
    },
  },
});
</script>