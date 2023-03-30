<template>
  <div>
    {{ title }} <br />
    <br />
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
        { name: "sam", number: 1, mark: 82 },
        { name: "annie", number: 2, mark: 87 },
        { name: "terin", number: 3, mark: 75 },
        { name: "alex", number: 4, mark: 95 },
      ],
      title: "STUDENT FORM",
    };
  },

  methods: {
    addList(name, number, mark) {
      this.classList.push({
        name: name,
        number: number,
        mark: mark,
      });
    },
  },
};
</script>

<style></style>
