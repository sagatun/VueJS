<template>
  <form @submit.prevent="handleSubmit">
    <div><label>Name</label><input v-model="name" type="text" /></div>
    <div><label>Phone</label><input v-model="phone" type="tel" /></div>
    <div><label>Email</label><input v-model="email" type="email" /></div>
    <div><button>Add Contact</button></div>
  </form>
</template>

<script>
export default {
  data() {
    return {
      name: '',
      phone: '',
      email: '',
    };
  },
  emits: ['handle-submit'],
  methods: {
    handleSubmit() {
      this.$emit('handle-submit', {
        name: this.name,
        phone: this.phone,
        email: this.email,
      });
      this.name = '';
      this.phone = '';
      this.email = '';
    },
  },
};
</script>
