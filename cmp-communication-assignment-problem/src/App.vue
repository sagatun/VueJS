<template>
  <div
    :style="{
      display: 'flex',
      justifyContent: 'space-around',
      alignItems: 'center',
    }"
  >
    <active-user :name="name" :age="age"></active-user
    ><user-data @submit-handler="handleSubmit"></user-data>
  </div>
</template>

<script>
import ActiveUser from './components/ActiveUser.vue';
import UserData from './components/UserData.vue';
export default {
  components: { ActiveUser, UserData },
  data() {
    return { name: '', age: '' };
  },
  methods: {
    handleSubmit(name, age) {
      (this.name = name), (this.age = age);
    },
  },
};
</script>
