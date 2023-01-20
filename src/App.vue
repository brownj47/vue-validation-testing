<template>
  <div id="app">
    <Form @submit="onSubmit">
      <Field type="email" name="email" />
      <button>Sign up for newsletter</button>
    </Form>
  </div>
</template>

<script>
import { Form, Field } from "vee-validate"

export default {
  components: {
    Form,
    Field
  },
  methods: {
    onSubmit() {
      console.log('Submitted');
    },
  },
}
</script>

<style>

</style>
