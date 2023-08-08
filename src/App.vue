<script setup>
import { computed, ref, watch } from "vue";
import HeaderComp from "./components/Header.vue";
//

const name = ref("");
const htmlText = ref("<div>Nguyen Van html</div>");
const hack = ref(
  `<a href="#" onclick="alert('Nguyen Van Hai')">Click de test</a`
);

const headingId = ref("headingId");
const headingClass1 = ref("headingClass1");
const headingClass2 = ref("headingClass2");
const isAccep = ref(false);
const hightlighColor = ref("orange");

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

const handleName = ref("NguyenVanHai");
const hanldeChange = () => {
  alert("Hai");
};

const num = ref(0);
const increment = (a, event) => {
  num.value = num.value + a;
  console.log(event);
};
const decrement = (a) => {
  num.value = num.value - a;
};

//
const formValues = ref({
  name: "",
  profileSumary: "",
  country: "",
  jobLocation: [],
  remoteWork: "yes",
  skillSet: [],
  yearOfEx: "",
});

const submitForm = () => {
  console.log(formValues);
};

const items = ref([
  {
    id: 1,
    title: "TV",
    price: 100,
  },
  {
    id: 2,
    title: "Watch",
    price: 200,
  },
]);

const totalPrice = computed(() => {
  return items.value.reduce((total, item) => total + item.price, 0);
});

watch(name, (newUsername, oldUsername) => {
  console.log(`Username changed from ${oldUsername} to ${newUsername}`);
});
</script>
<template>
  <HeaderComp />
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

  <!-- !Event Handling -->
  <div>
    <h2>{{ handleName }}</h2>
    <button @click="hanldeChange">Click để đổi tên</button>
  </div>

  <div style="display: flex; margin-top: 50px">
    <button @click="increment(5, $event)">+</button>
    <h2>{{ num }}</h2>
    <button @click="decrement(5)">-</button>
  </div>

  <!-- !Form handling -->
  <div>
    <pre>
      {{ JSON.stringify(formValues.name, null, 2) }}
      {{ JSON.stringify(formValues.profileSumary, null, 2) }}
      {{ JSON.stringify(formValues.country, null, 2) }}
      {{ JSON.stringify(formValues.jobLocation, null, 2) }}
      {{ JSON.stringify(formValues.remoteWork, null, 2) }}
      {{ JSON.stringify(formValues.skillSet, null, 2) }}


    </pre>
  </div>
  <form @submit.stop.prevent="submitForm">
    <!-- !FORM INPUT -->
    <div>
      <label for="name">Name</label>
      <input type="text" name="name" id="name" v-model.lazy="formValues.name" />
    </div>
    <!-- !FORM AREA -->
    <div>
      <label for="profileSumary">ProfileSumary</label>
      <textarea
        name="profileSumaryprofileSumary"
        id="profileSumary"
        cols="30"
        rows="10"
        v-model="formValues.profileSumary"
      ></textarea>
    </div>
    <!--!FORM SELECT  -->
    <div>
      <label for="country">Country</label>
      <select name="country" id="country" v-model="formValues.country">
        <option value="">Select country</option>
        <option value="vietnam">Việt Nam</option>
        <option value="nhatban">Nhật Bản</option>
        <option value="hanquoc">Hàn Quốc</option>
      </select>
    </div>
    <!-- !FORM SELECT MULTIPLE -->
    <div>
      <label for="job-location">Job Location</label>
      <select
        name="job-location"
        id="job-location"
        multiple
        v-model="formValues.jobLocation"
      >
        <option value="">Select country</option>
        <option value="vietnam">Việt Nam</option>
        <option value="nhatban">Nhật Bản</option>
        <option value="hanquoc">Hàn Quốc</option>
      </select>
    </div>
    <!-- !FORM CHECKBOX -->
    <div>
      <input
        type="checkbox"
        name="remoteWork"
        id="remoteWork"
        v-model="formValues.remoteWork"
        true-value="yes"
        false-value="no"
      />
      <label for="remoteWork">Open to remote work</label>
    </div>
    <!-- !FORM  MULTI CHECKBOX -->
    <div>
      <label> SkillSet</label>
      <input
        type="checkbox"
        name="html"
        id="html"
        value="html"
        v-model="formValues.skillSet"
      />
      <label for="html">HTML</label>
      <input
        type="checkbox"
        name="css"
        id="css"
        value="css"
        v-model="formValues.skillSet"
      />
      <label for="css">CSS</label>
      <input
        type="checkbox"
        name="js"
        id="js"
        value="js"
        v-model="formValues.skillSet"
      />
      <label for="js">JS</label>
    </div>
    <button type="submit">Lưu</button>
  </form>
  <div>
    <h2>Tổng tiền này</h2>
    <span>{{ totalPrice }}</span>
  </div>

  <div>
    <input v-model="name" placeholder="Enter your username" />
    <p>Current Username: {{ name }}</p>
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
