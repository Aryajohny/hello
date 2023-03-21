<template>
  <div>
    {{ testProp }} <br />
    <input v-model="name" type="text" placeholder="enter name" class="grey" />
    <br />
    <br />
    <input v-model="email" type="text" placeholder="enter email" class="grey" />
    <br /><br />
    <p>Gender</p>
    <input type="checkbox" value="male" id="male" />
    <label for="male">male</label>
    <br /><br />
    <input type="checkbox" value="female" id="female" />
    <label for="female">female</label>
    <br /><br />
    <p>Hobbies</p>
    <div v-for="hobby in hobbyList" :key="hobby.id">
      <input type="checkbox" :value="hobby.id" :id="hobby.id" />
      <label :for="hobby.id"> {{ hobby.id }} </label>
      <br /><br />
    </div>

    <input
      v-model="newHobby"
      type="text"
      placeholder="enter newHobby"
      class="grey"
    />
    <br />
    <button type="button" @click="addHobby">add!</button>
    <br /><br />
    <button type="button" @click="submit">submit!</button>
    <br />

    {{ formatText }}
  </div>
</template>

<script>
export default {
  data() {
    return {
      hobbyList: [
        { id: "sports", label: "Sports" },
        { id: "dance", label: "Dance" },
        { id: "travel", label: "Travel" },
        { id: "movie", label: "movie" },
      ],

      name: "",
      email: "",
      Gender: "",
      Hobbies: "",
      newHobby: "",
    };
  },
  mounted() {
    console.log("application mounted");
  },
  created() {
    console.log("application created");
  },
  destroyed() {
    console.log("application destroyed");
  },

  computed: {
    formatText() {
      if (this.name) {
        return "my name is " + this.name;
      } else {
        return "nothing";
      }
    },
  },
  watch: {
    name(newVal, oldVal) {
      console.log("hi " + newVal + " " + oldVal);
    },
  },
  props: {
    testProp: {
      type: String,
      default: "",
    },
  },
  methods: {
    submit() {
      if (this.name) {
        this.$emit("submitted", "hello" + this.name);
      } else {
        this.$emit("submitted", "pls call me something");
      }
    },
    addHobby() {
      this.hobbyList.push({ id: this.newHobby, label: this.newHobby });
      this.newHobby = "";
    },
  },
};
</script>

<style></style>
