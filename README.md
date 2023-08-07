# Vue 3 + Vite

This template should help get you started developing with Vue 3 in Vite. The template uses Vue 3 `<script setup>` SFCs, check out the [script setup docs](https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup) to learn more.

## Recommended IDE Setup

- [VS Code](https://code.visualstudio.com/) + [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (and disable Vetur) + [TypeScript Vue Plugin (Volar)](https://marketplace.visualstudio.com/items?itemName=Vue.vscode-typescript-vue-plugin).

## DAY 1

1. Vue.Js là gì?
   Vue.js là một framework JavaScript mã nguồn mở được sử dụng để xây dựng giao diện người dùng và ứng dụng web tương tác. Nó tập trung vào việc tạo giao diện người dùng phản hồi, cung cấp hệ thống reactivity tự động và hỗ trợ các tính năng mạnh mẽ để giúp bạn xây dựng ứng dụng một cách dễ dàng và hiệu quả. Vue.js sử dụng cú pháp đơn giản và dễ đọc, hỗ trợ kiến trúc dựa trên thành phần và tích hợp linh hoạt với các thư viện và công nghệ khác. Nó đã trở thành một trong những framework phổ biến và được ưa chuộng trong cộng đồng phát triển web.

2. Tại sao sử dụng Vue.Js?

   1. Dễ tiếp cận
   2. Linh hoạt
   3. Hiệu suất cao

3. Cài đặt và sử dụng thư viện
4. Cấu trúc dự án
5. Single File Components

<template></template>

<script></script>

<style></style>

or Vite:

<script></script>

<template></template>

<style></style>

6. Binding Text
7. Binding html
8. Binding attributes
9. Binding Classes
10. Binding Styles
11. Conditional Rendering
    1. v-if
    2. v-else
    3. v-else-if
    4. v-show
12. List rendering

    1. v-for

13. Lists and Keys
14. Conditional List Rendering
15. Method

# Note

1. Khai báo dữ liệu đơn giản với ref:
   <script setup>
   import { ref } from "vue";
   const count = ref(0);
   </script>
   <!--  -->
2. Khai báo object reactive với reactive:
   <script setup>
   import { reactive } from "vue";
   const user = reactive({
   name: "Nguyen Van Hai",
   email: "nguyenvanhai@example.com",
   age: 30,
   });
   </script>
   <!--  -->
3. Khai báo mảng reactive với reactive hoặc ref:
   <script setup>
   import { ref } from "vue";
   const colors = ref(["red", "green", "blue"]);
   </script>
   <!--  -->
4. Khai báo computed property với computed:
   <script setup>
   import { ref, computed } from "vue";
   const count = ref(0);
   const doubledCount = computed(() => count.value \* 2);
   </script>
   <!--  -->
5. Khai báo hàm reactive với ref hoặc reactive:
   <script setup>
   import { ref } from "vue";
   const inputValue = ref("");
   const handleChange = () => {
       };
   // Xử lý thay đổi giá trị của inputValue
   </script>
   <!--  -->
