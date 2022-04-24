<template>
  <!-- Calling the addStudent method and passing the  object to it. -->
  <StudentInput @addStudent="addStudent($event)" />

  <!-- A loop that iterates over the schuelerListe array and creates a new
  Schueler component for each // element in the array. -->
  <template v-for="schueler in schuelerListe" :key="schueler.id">
    <Schueler
      :id="schueler.id"
      :name="schueler.name"
      :age="schueler.age"
      :telNumber="schueler.telNumber"
      @deleteStudent="deleteT($event)"
    />
  </template>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Schueler from "@/components/Schueler.vue"; // @ is an alias to /src
import StudentInput from "@/components/StudentInput.vue"; // @ is an alias to /src

export default defineComponent({
  name: "SchuelerView",
  components: {
    Schueler,
    StudentInput,
  },
  methods: {
    // A method that is called when the delete button is clicked. It takes the index of the student
    // that was clicked and removes it from the array.
    deleteT(schueler: number) {
      // Finding the index of the student that was clicked
      let del = this.schuelerListe.findIndex(
        (student) => student.id == schueler
      );

      this.schuelerListe.splice(del, 1);
      console.log("got deleted ❤️‍🔥!" + schueler);
      console.log(this.schuelerListe);
    },
    // A method that is called when the addStudent button is clicked. It takes the object that was
    // passed to it and adds it to the array.
    addStudent(schueler: any) {
      let student: any = {
        name: schueler.firstname + " " + schueler.lastname,
        age: schueler.age,
        telNumber: schueler.telNumber,
        id: this.schuelerListe.length,
      };
      this.schuelerListe.push(student);
      console.log("something happened");
    },
  },
  data: () => ({
    // An array of objects.
    schuelerListe: [
      {
        id: 0,
        name: "Leanne Graham",
        age: 18,
        telNumber: "+43 655 1234576",
      },
      {
        id: 1,
        name: "Leon Bauer",
        age: 19,
        telNumber: "+43 655 7654321",
      },
      {
        id: 2,
        name: "Leonie Trauer",
        age: 21,
        telNumber: "+43 655 0989004",
      },
    ],
  }),
});
</script>
