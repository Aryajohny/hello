<template>
  <div>
    <input type="text" v-model="name" placeholder="enter name" class="grey" />

    <br />
    <br />
    <input
      type="text"
      v-model="number"
      placeholder="enter number"
      class="grey"
    />

    <br /><br />
    <input type="text" v-model="mark" placeholder="enter mark" class="grey" />
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
      mark: "",
    };
  },

  methods: {
    submit() {
      if (this.name === "" || this.number === "" || this.mark === "") {
        window.alert("pls fill the box.");
      } else if (isNaN(this.number)) {
        window.alert("invalid number.");
      } else if (isNaN(this.mark)) {
        window.alert("invalid mark.");
      } else {
        this.$emit("submitted", this.name, this.number, this.mark);
        (this.name = ""), (this.number = ""), (this.mark = "");
      }
    },
  },
};
</script>

<style></style>
