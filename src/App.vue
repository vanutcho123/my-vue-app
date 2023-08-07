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
