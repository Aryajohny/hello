<template>
  <div>
    <user-form @submitted="handleSubmitted" :testProp="title" />
  </div>
</template>

<script>
import UserForm from "~/components/UserForm.vue";
export default {
  components: { UserForm },
  data() {
    return {
      title: "USER FORM",
    };
  },
  methods: {
    handleSubmitted(msg) {
      window.alert(msg);
    },
  },
};
</script>

<style></style>
