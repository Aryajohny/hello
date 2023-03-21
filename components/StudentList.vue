<template>
  <div>
    {{ addprop }} <br /><br />
    <p>classList</p>
    <table border="10px">
      <tr>
        <td>name</td>
        <br />
        <td>number</td>
      </tr>
      <tr v-for="students in classList" :key="students.id">
        <td>{{ students.name }}</td>
        <br />
        <td>{{ students.number }}</td>
      </tr>
    </table>
    <br /><br />
  </div>
</template>

<script>
export default {
  props: {
    classList: {
      type: Array,
      default: [],
    },
  },
  methods: {},
};
</script>

<style></style>
