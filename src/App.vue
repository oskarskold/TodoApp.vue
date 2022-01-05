<template>
  <div id="app">
    <section>
      <h1>My todo list</h1>
      <aside>
        <input type="text" v-model="enteredGoalValue" />
        <button @click="addGoal">Add todo</button>
      </aside>
      <p v-if="goals.length === 0">
        No goals have been added yet - please start adding some!
      </p>
      <ul v-else>
        <li v-for="goal in goals" :key="goal">{{ goal }}</li>
      </ul>
    </section>
  </div>
</template>

<script>
export default {
  data() {
    return {
      enteredGoalValue: "",
      goals: [],
    };
  },
  methods: {
    addGoal() {
      this.goals.push(this.enteredGoalValue);
    },
  },
};
</script>

<style>
div {
  display: flex;
  justify-content: center;
}
section {
  padding: 1rem 2rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  border: 1px solid black;
  box-shadow: 5px 5px 40px 5px #505050;
}
h1 {
  color: rgb(20, 88, 100);
  font-weight: 900;
  font-family: Verdana, Geneva, Tahoma, sans-serif;
  border-bottom: 4px solid grey;
}

input {
  border: 1px solid rgb(157, 156, 156);
}
button {
  background: rgb(31, 136, 155);
  color: white;
  border: 1px solid rgb(48, 121, 131);
}
ul {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 2rem;
}
li {
  margin: 0.5rem;
  background: rgba(28, 103, 116, 0.487);
  list-style-type: none;
  padding: 0.5rem 6rem;
  text-align: center;
  border-radius: 5px;
  font-family: Verdana, Geneva, Tahoma, sans-serif;
  letter-spacing: 0.1rem;
  font-weight: 600;
  font-size: 0.9rem;
}
</style>
