<template>
  <div>
    <student-list :classList="classList" />
    <student-form @submitted="addList" />
    <br />
  </div>
</template>

<script>
import StudentForm from "~/components/StudentForm.vue";
import StudentList from "~/components/StudentList.vue";

export default {
  components: { StudentForm, StudentList },
  data() {
    return {
      classList: [
        { name: "sam", number: 1 },
        { name: "annie", number: 2 },
        { name: "terin", number: 3 },
        { name: "alex", number: 4 },
      ],
      title: "STUDENT FORM",
    };
  },

  methods: {
    addList(name, number) {
      this.classList.push({
        name: name,
        number: number,
      });
    },
  },
};
</script>

<style></style>
