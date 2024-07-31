<script setup>
import { computed, ref, watch } from 'vue';

// import UserList from '@/components/UserList.vue';
// import UserDetail from '@/components/UserDetails.vue';

const userList = ref([])
const selectedUser = ref(null);

   fetch('https://jsonplaceholder.typicode.com/users')
  .then((response) => response.json())
  .then((json) => userList.value = json)

  const selectUser = (user) => {
  selectedUser.value = user;
};

</script>

<template>
    <!-- <UserList @userSelected="handleUserSelected" />
    <UserDetail :user="selectedUser" /> -->
    <ul  >
      <li v-for="user in userList" @click="selectUser(user)">{{ user.username }}</li>
    </ul >


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
  ul{
    list-style-type: none
  }
  li:hover{
    cursor: pointer;
    text-decoration: none
  }
</style>
