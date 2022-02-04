<template>
  <ul>
    <LearningResources />
  </ul>
</template>

<script>
import LearningResources from './components/learning-resources/LearningResources.vue';
export default {
  components: { LearningResources },

  data() {
    return {
      storedResources: [
        {
          id: 'official-guide',
          title: 'Official Guide',
          description: 'The official Vue.js documentation',
          link: 'https://vuejs.org',
        },
        {
          id: 'google',
          title: 'Google',
          description: '...learn to google',
          link: 'https://google.com',
        },
      ],
    };
  },
};
</script>
