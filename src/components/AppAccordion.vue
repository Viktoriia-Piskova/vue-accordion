<template>
  <div>
    <button
      @click="toggleAccordion()"
      class="accordion"
      :aria-expanded="isOpen"
      :aria-controls="`collapse${_uid}`"
    >
      {{ title }}

      <svg
        :class="{
          'rotate-180': isOpen,
          'rotate-0': !isOpen,
        }"
        fill="none"
        stroke="currentColor"
        xmlns="http://www.w3.org/2000/svg"
        viewBox="0 0 16 10"
        aria-hidden="true"
        height="5px"
        width="10px"
      >
        <path
          d="M15 1.2l-7 7-7-7"
          stroke-width="2"
          stroke-linecap="round"
          stroke-linejoin="round"
        />
      </svg>
    </button>

    <div v-show="isOpen" :id="`collapse${_uid}`">
      <form action="/action_page.php">
        <template v-for="(option, index) in description" :key="index">
          <input type="radio" :id="index" :name="index" :value="index" />
          <label :for="index">{{ option }}</label
          ><br />
        </template>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isOpen: false,
    };
  },
  props: {
    title: {
      type: String,
    },
    description: {
      type: String,
    },
  },
  methods: {
    toggleAccordion() {
      this.isOpen = !this.isOpen;
    },
  },
};
</script>

<style scoped>
.accordion {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin: 16px;
}
</style>
