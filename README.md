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
16. EventHandling
17. Form Handling

    1. Capture user input
    2. Inputs
    3. Textarea
    4. Single select dropdown control
    5. Multi select control
    6. Checkout
    7. Checkbox group
    8. Radio
    9. Submit form data
       <!-- Hiển thị dữ liệu để xem khi nhập form -->
       {{ JSON.stringify(formValues.country, null, 2) }}

18. Modifiers
    Các Modifier cho v-on:
    .stop: Ngăn chặn sự lan truyền của sự kiện. Tương đương với event.stopPropagation().
    .prevent: Ngăn chặn hành vi mặc định của sự kiện. Tương đương với event.preventDefault().
    .capture: Lắng nghe sự kiện trong giai đoạn capture (từ gốc tới mục tiêu).
    .self: Chỉ kích hoạt xử lý sự kiện nếu mục tiêu của sự kiện là chính phần tử đó (không phải từ con cháu).
    .once: Bộ lắng nghe sự kiện sẽ tự động được loại bỏ sau lần kích hoạt đầu tiên.
    .passive: Đánh dấu bộ lắng nghe sự kiện là passive, giúp cải thiện hiệu suất cuộn trên các thiết bị cảm ứng.
    Ví dụ:

<!-- Ngăn chặn lan truyền và ngăn chặn hành vi mặc định -->

<button @click.stop.prevent="doSomething">Nhấn vào tôi</button>

<!-- Lắng nghe sự kiện trong giai đoạn capture -->
<div @click.capture="doSomething">Capture Phase</div>

<!-- Chỉ kích hoạt xử lý nếu mục tiêu của sự kiện là phần tử đó -->
<div @click.self="doSomething">Nhấn vào tôi</div>

<!-- Bộ lắng nghe sự kiện sẽ bị loại bỏ sau lần nhấp đầu tiên -->

<button @click.once="doSomething">Nhấn một lần</button>

<!-- Đánh dấu bộ lắng nghe sự kiện là passive để cải thiện hiệu suất cuộn -->
<div @touchstart.passive="handleTouchStart">Chạm vào tôi</div>

Các Modifier cho v-model:
.lazy: Cập nhật giá trị liên kết chỉ khi sự kiện change được kích hoạt (thường sau khi input mất focus).
.number: Chuyển đổi giá trị nhập vào thành số trước khi liên kết.
.trim: Loại bỏ khoảng trắng đầu và cuối chuỗi nhập vào trước khi liên kết.
Ví dụ:

<!-- Cập nhật giá trị chỉ khi input mất focus -->
<input v-model.lazy="message">

<!-- Chuyển đổi giá trị nhập vào thành số -->
<input v-model.number="age" type="number">

<!-- Loại bỏ khoảng trắng đầu và cuối chuỗi -->
<input v-model.trim="username">
Những ví dụ trên chỉ là một số ví dụ về cách sử dụng các modifier trong các hướng dẫn của Vue.js để tùy chỉnh cách chúng hoạt động. Các modifier giúp bạn điều chỉnh tương tác trong các thành phần của bạn, làm cho mã của bạn trở nên chính xác và thể hiện. Hãy nhớ rằng các modifier chỉ tồn tại cho một số chỉ thị cụ thể và sự có sẵn của chúng có thể thay đổi tùy theo chỉ thị bạn đang sử dụng.

19. Computed Properties

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
