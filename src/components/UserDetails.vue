<script setup>
import { computed, ref, watch } from 'vue';

</script>

<template>

    <div v-if="selectedUser" >
    <h2>Информация о пользователе</h2>
    <p><strong>Имя:</strong> {{ selectedUser.name }}</p>
    <p><strong>Email:</strong> {{ selectedUser.email }}</p>
    <p><strong>Телефон:</strong> {{ selectedUser.phone }}</p>
    <p><strong>Веб - Сайт:</strong> {{ selectedUser.website }}</p>
    <p><strong>Компания</strong> {{ selectedUser.company.name }}</p>

  </div>
    


</template>

<style scoped>

</style>
