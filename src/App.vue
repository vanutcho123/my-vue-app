<script setup>
import { ref } from "vue";
//
const name = ref("Nguyen Van text");
const htmlText = ref("<div>Nguyen Van html</div>");
const hack = ref(
  `<a href="#" onclick="alert('Nguyen Van Hai')">Click de test</a`
);

const headingId = ref("headingId");
const headingClass1 = ref("headingClass1");
const headingClass2 = ref("headingClass2");
const isAccep = ref(false);
const hightlighColor = ref("orange");

const num = ref(1);

const showElement = ref(false);

const names = ref(["Hai", "Dong", "Bin"]);
const fullName = ref([
  {
    firstName: "Nguyen",
    lastName: "Hai",
  },
  {
    firstName: "Nguyen",
    lastName: "Tu",
  },
]);

const actors = ref([
  {
    name: "Thành",
    movies: ["Phim 1", "Phim 2", "Phim 3"],
  },
  {
    name: "Tú",
    movies: ["Phim 4", "Phim 5"],
  },
]);

const add = (a, b, c) => {
  return a + b + c;
};

const baseMultiplier = ref(5);
const multipy = (a) => {
  return baseMultiplier.value * a;
};
</script>
<template>
  <!-- !Binding Text -->
  <!-- Interpolation  -->
  <div>Nguyễn Văn Hải {{ name }}</div>
  <!--V-text  -->
  <div v-text="name"></div>
  <!-- !Binding Html -->
  <!-- V-html -->
  <div v-html="htmlText"></div>
  <div v-html="hack"></div>
  <button @click="handleClick">Click me</button>
  <!-- !Binding attributes -->
  <div v-bind:class="headingClass1">Đây là v-bind:class</div>
  <div v-bind:id="headingId">Đây là v-bind:id</div>
  <div v-bind:class="[headingClass1, headingClass2]">Đây là 2 class</div>
  <!-- !Binding Classes -->
  <a href="#" class="underline">Underline</a>
  <h2 v-bind:class="isAccep ? 'red' : 'blue'">Đây là Binding Classes</h2>
  <!-- !Binding Styles -->
  <h3
    v-bind:style="{
      color: hightlighColor,
    }"
  >
    Đây là binding Style
  </h3>
  <!-- !Conditional Rendering -->
  <!-- v-if v-else v-else-if -->
  <div>
    <h3 v-if="num === 0">Element num = 0</h3>
    <h3 v-else>Element num #0</h3>
  </div>
  <!-- v-show -->
  <div v-show="showElement">Show element</div>
  <!-- !List Rendering -->
  <ul>
    <li v-for="(name, index) in names" :key="index">{{ name }}</li>
  </ul>
  <!--  -->
  <ul>
    <li v-for="i in fullName" :key="i">
      <a href="#">{{ i.firstName }}</a>
      <span>{{ i.lastName }}</span>
    </li>
  </ul>
  <!--  -->

  <ul>
    <li v-for="actor in actors" :key="actor.name">
      <h2>{{ actor.name }}</h2>
      <div v-for="(a, key, index) in actor.movies" :key="index">
        {{ index }}{{ key }}{{ a }}
      </div>
    </li>
  </ul>
  <!-- !List and key -->
  <div v-for="name in names" :key="name">
    <h2 v-if="name === 'Hai'">{{ name }}</h2>
  </div>

  <!-- !Method -->
  <div>
    <h2>{{ 2 + 3 + 5 }}</h2>
    <h2>{{ 5 + 10 + 15 }}</h2>
    <h2>Add method - {{ add(1, 2, 6) }}</h2>
    <h2>hehe - {{ multipy(3) }}</h2>
  </div>
</template>

<style scoped>
/* !Binding Classes */
.underline {
  text-decoration: none;
}
.red {
  color: red;
}
.blue {
  color: blue;
}
</style>
