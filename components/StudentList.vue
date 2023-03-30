<template>
  <div>
    <p>classList</p>
    <table border="10px">
      <tr>
        <td>name</td>
        <br />
        <td>number</td>
        <br />
        <td>mark</td>
      </tr>
      <tr v-for="students in classList" :key="students.id">
        <td>{{ students.name }}</td>
        <br />
        <td>{{ students.number }}</td>
        <br />
        <td>{{ students.mark }}</td>
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
};
</script>

<style></style>
