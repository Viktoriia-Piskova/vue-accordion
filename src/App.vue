<template>
  <app-accordion
    v-for="post in posts"
    :key="post.id"
    :title="post.title"
    :description="post.description"
  >
  </app-accordion>
</template>

<script>
import AppAccordion from "./components/AppAccordion.vue";

export default {
  name: "App",
  data() {
    return {
      posts: [
        {
          id: 1,
          title: "To take into account on user level data",
          description: [
            "Do you have one user in more than one variant of the same AB test?",
            "Are you users actually getting the treatment we expect them to get?",
            "Do we have enough users in our AB test? Are those users representative for the total population?",
          ],
        },
        {
          id: 2,
          title: "To take into account on user level data",
          description: [
            "Do you have one user in more than one variant of the same AB test?",
            "Are you users actually getting the treatment we expect them to get?",
            "Do we have enough users in our AB test? Are those users representative for the total population?",
          ],
        },
        {
          id: 3,
          title: "To take into account on user level data",
          description: [
            "Do you have one user in more than one variant of the same AB test?",
            "Are you users actually getting the treatment we expect them to get?",
            "Do we have enough users in our AB test? Are those users representative for the total population?",
          ],
        },
      ],
    };
  },
  components: {
    AppAccordion,
  },
};
</script>

<style lang="scss">
#app {
  font-family: "Montserrat";
  font-style: normal;
  font-weight: 600;
  font-size: 14px;
  line-height: 24px;
  color: #0d2a54;
}
</style>
