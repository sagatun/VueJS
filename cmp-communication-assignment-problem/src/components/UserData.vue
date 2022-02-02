<template>
  <form @submit.prevent="submitHandler">
    <label>Name: </label><input v-model="name" type="text" />
    <label>Age: </label><input v-model="age" type="text" />
    <button>Submit</button>
  </form>
</template>

<script>
export default {
  data() {
    return { name: '', age: '' };
  },
  emits: ['submit-handler'],
  methods: {
    submitHandler() {
      this.$emit('submit-handler', this.name, this.age);
    },
  },
};
</script>
