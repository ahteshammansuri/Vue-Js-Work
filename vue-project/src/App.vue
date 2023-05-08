<template lang="">
  <div>
    <h4>Name : {{name}}</h4>
    <h4>Email : {{email}}</h4>
    <div v-html="html"></div>
    <div :id="divId">This div has Attribute id</div>
    <div class="demo">This is new class</div>
    <div :class="isCompleted ? 'done' : 'remaining'">Classs Binding Div</div>
    <div v-if="num === 0">Number is Zero</div>
    <div v-else-if="num < 0">Number Is Nagetive</div>
    <div v-else-if="num > 0">Number Is Positive</div>
    <!-- <div v-else="num">Number Is Not A Zero</div> -->

    <div v-for="item in data">
      <li>{{item.name}}</li>
    </div>

    <button @click="btnClick++">Click {{btnClick}}</button>

    <div>
      This is click value {{btnClick}}
    </div>

    <button v-on:click="getApiData(true)">Get Api Data</button>

    <!-- {{apiClick}} -->

    {{val}}
    <div v-for="item in getApiData()" >
      <p>{{item.name}}</p>
    </div>

  </div>
</template>
<script>
// import { ref } from "vue";

// const apiClick = ref(false);

export default {
  data() {
    return {
      name: "Ahtesham",
      email: "ahtesham@gmail.com",
      html: "<h1>Hellio</h1>",
      divId: "headerDiv",
      bindClass: "remaining",
      isCompleted: true,
      num: 5,
      btnClick: 0,
      apiClick: false,
      // data: [{name:"joe doe", email:"joe@gmail.com"}, {name:"mati rives", email:"mat@gmail.com"}],
    }
  },
  methods: {
    async getApiData(value) {
      this.apiClick = value;
      const apiData = await fetch('https://jsonplaceholder.typicode.com/users').then(response => response.json());
      console.log(apiData);
      // if (!apiData.length ) {
      //   this.apiClick = false;
      // }
      return apiData;
    }
  },
}

</script>
<style>
.done {
  color: rgb(0, 255, 64);
  font-size: larger;

}

.remaining {
  color: rgb(226, 43, 43);
  font-size: larger;
}
</style>