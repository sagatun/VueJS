<template>
  <li>
    <h2>{{ isFavorite ? name + ' (is favorite)' : name }}</h2>
    <button @click="toggleDetails">
      {{ detailsAreVisible ? 'Hide' : 'Show' }}
    </button>
    <button @click="toggleFavorite">Toggle Favorite</button>
    <ul v-if="detailsAreVisible">
      <li><strong>Phone: </strong>{{ phoneNumber }}</li>
      <li><strong>Email: </strong>{{ email }}</li>
    </ul>
    <button @click="deleteContact">Delete</button>
  </li>
</template>

<script>
export default {
  // props: ['name', 'phoneNumber', 'email', 'isFavorite'],
  props: {
    id: { type: String, required: true },
    name: { type: String, required: true },
    phoneNumber: { type: String, required: true },
    email: { type: String, required: true },
    isFavorite: { type: Boolean, required: false, default: false },
  },
  emits: ['toggle-favorite', 'delete-contact'],
  // emits: {
  //   'toggle-favorite': function (id) {
  //     if (id) {
  //       return true;
  //     } else {
  //       console.warn('Id is missing');
  //       return false;
  //     }
  //   },
  // },
  data() {
    return {
      detailsAreVisible: false,
    };
  },
  methods: {
    toggleDetails() {
      this.detailsAreVisible = !this.detailsAreVisible;
    },
    toggleFavorite() {
      this.$emit('toggle-favorite', this.id);
    },
    deleteContact() {
      this.$emit('delete-contact', this.id);
    },
  },
};
</script>
