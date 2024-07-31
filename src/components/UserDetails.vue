<script setup>
const props = defineProps({
  user: Object,
})
</script>

<template>

    <div >
      <h2>Информация о пользователе</h2>
      <p><strong>Имя:</strong> {{ user.name }}</p>
      <p><strong>Email:</strong> {{ user.email }}</p>
      <p><strong>Телефон:</strong> {{ user.phone }}</p>
      <p><strong>Веб - Сайт:</strong> {{ user.website }}</p>
      <p><strong>Компания</strong> {{ user.company.name }}</p>
  </div>
    

</template>

<style scoped>

</style>
