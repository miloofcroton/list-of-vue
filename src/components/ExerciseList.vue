<template>
  <section>
    <h3>Upper Body</h3>
    <ul>
      <Exercise
        v-for="exercise in exercises"
        v-if="exercise.type === 'upper'"
        v-bind:key="exercise.name"
        v-bind:exercise="exercise"
        v-bind:onRemove="onRemove"
      />
    </ul>
    <h3>Lower Body</h3>
    <ul>
      <Exercise
        v-for="exercise in exercises"
        v-if="exercise.type === 'lower'"
        v-bind:key="exercise.name"
        v-bind:exercise="exercise"
        v-bind:onRemove="onRemove"
      />
    </ul>
    <h3>Core</h3>
    <ul>
      <Exercise
        v-for="exercise in exercises"
        v-if="exercise.type === 'core'"
        v-bind:key="exercise.name"
        v-bind:exercise="exercise"
        v-bind:onRemove="onRemove"
      />
    </ul>
  </section>
</template>

<script>
import Exercise from './Exercise.vue';

export default {
  
  props: {
    exercises: Array,
    onRemove: Function
  },

  components: {
    Exercise,
  }

};
</script>

<style scoped>

* {
    color: rgb(0, 0, 68);
}

section {
    margin: 10px 5%;
}
h2 {
    font-size: 48px;
}
h3 {
    font-size: 32px;
    margin: 10px 0px 20px 0px;
}
ul {
  list-style: none;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  border: 1px solid rgb(0, 0, 68);
  border-radius: 10px;
  box-shadow: 0 2px 4px 0 rgba(0,0,0,0.5);
}

</style>
