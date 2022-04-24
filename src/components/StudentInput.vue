<template>
  <div class="row">
    <form class="col s12">
      <div class="row"><h1>Enter a new Student 🤩</h1></div>
      <div class="row">
        <div class="input-field col s6">
          <i class="material-icons prefix">account_circle</i>
          <input id="firstname" type="text" class="validate" />
          <label for="firstname">First Name</label>
        </div>
        <div class="input-field col s6">
          <i class="material-icons prefix">account_box</i>
          <input id="lastname" type="text" class="validate" />
          <label for="lastname">Last Name</label>
        </div>
      </div>
      <div class="row">
        <div class="input-field col s6">
          <i class="material-icons prefix">cake</i>
          <input id="age" type="number" class="validate" />
          <label for="age">Age</label>
        </div>
        <div class="input-field col s6">
          <i class="material-icons prefix">phone</i>
          <input id="tel" type="tel" class="validate" />
          <label for="tel">Telephone</label>
        </div>
      </div>
    </form>
    <div class="row">
      <a class="waves-effect waves-light btn"
        ><i class="material-icons right">add_circle_outline</i>add</a
      >
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "@vue/runtime-core";
export default defineComponent({
  methods: {
    addSchueler() {
      this.$emit("addStudent");
    },
  },
});
</script>