<template>
  <div>
    {{ addprop }} <br /><br />
    <input v-model="name" type="text" placeholder="enter name" class="grey" />
    <br />
    <br />
    <input
      v-model="number"
      type="text"
      placeholder="enter number"
      class="grey"
    />
    <br /><br />
    <button type="button" @click="submit">submit!</button>
    <br /><br />
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: "",
      number: "",
    };
  },
  methods: {
    submit() {
      this.$emit("submitted", this.name, this.number);
    },
  },
  prop: {
    addprop: {
      type: String,
      default: "",
    },
  },
};
</script>

<style></style>
