<template>
  <div id="app">
    <Form @submit="onSubmit">
      <Field type="email" name="email" :rules="validateEmail" />
      <ErrorMessage name="email"/>
      <button>Sign up for newsletter</button>
    </Form>
  </div>
</template>

<script>
import { Form, Field, ErrorMessage } from "vee-validate"

export default {
  components: {
    Form,
    Field,
    ErrorMessage
  },
  methods: {
    onSubmit(values) {
      console.log(values);
    },
    validateEmail(value){
      if (!value){
        return "this field is required";
      }
      const regex = /^[A-Z0-9._%+-]+@[A-Z0-9.-]+\.[A-Z]{2,4}$/i;
      if (!regex.test(value)) {
        return 'This field must be a valid email';
      }
      // All is good
      return true;
    }
  },
}
</script>

<style>

</style>
