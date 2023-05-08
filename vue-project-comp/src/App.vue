
<template>
  <div v-if="inCompletedTask.length" class="sectionIncompleted">
    <h3> In Completed Task </h3>
    <label v-for="item in inCompletedTask" :key="item.id">
      <br>
      {{ item.name }}
      <input type="checkbox" name="" id="" v-model="item.completed">
    </label>
  </div>

  <br>
  <div v-if="completedTask.length" class="sectionCompleted">
    <br>
    <h3> Completed Task </h3>
    <label v-for="item in completedTask" :key="item.id">
      <br>
      {{ item.name }}
      <input type="checkbox" name="" id="" v-model="item.completed">
    </label>
  </div>

  <!-- <app-button></app-button> -->
  <MyComponent></MyComponent>
</template>

<script>
// import { Vue } from "vue";
import MyComponent from './components/TestButton.vue';
export default {
  data() {
    return {
      tasks: [{ id: 1, name: "First Project", completed: false }, { id: 2, name: "Second Project", completed: false }, { id: 3, name: "Third Project", completed: false }]
    }
  },
  computed: {
    inCompletedTask() {
      return this.tasks.filter(a => !a.completed);
    },
    completedTask() {
      return this.tasks.filter(a => a.completed);
    }
  },

  components:{
    MyComponent,
  }

  // components: {
  //   "app-button": {
  //     template: `
  //    <div><h1> Heloojdfh jhfdh </h1></div>
  //    `,
      // mounted() {
      //   alert("fHello")
      // }
  //   },
  // },
  // mounted() {
  //   Vue.createApp(this).mount('#app');
  // }

}
</script>

<style scoped>
header {
  line-height: 1.5;
  max-height: 100vh;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}
</style>
