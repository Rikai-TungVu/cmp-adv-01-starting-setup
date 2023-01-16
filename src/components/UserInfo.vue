<template>
  <section>
    <base-card>
    <!-- Component BaseCard đã được khai báo vs định nghĩa ở main.js -->
      <template v-slot:header>
      <!-- <template #header> -->
        <!-- nối slot vàp template bằng v-slot -->
        <h2>{{ fullName }}</h2>
        <base-badge :type="role" :caption="role.toUpperCase()"></base-badge>
      </template>
      <template v-slot:default>
        <p>{{ infoText }}</p>
      </template>
    </base-card>
  </section>
</template>

<script>
export default {
  props: ['fullName', 'infoText', 'role'],
};
</script>