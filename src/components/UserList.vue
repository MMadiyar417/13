<script setup>
import { computed, ref, watch } from 'vue';

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

    <ul  >
      <li v-for="user in userList" @click="selectUser(user)">{{ user.username }}</li>
    </ul >

</template>

<style scoped>
  ul{
    list-style-type: none
  }
  li:hover{
    text-decoration: none;
    cursor: pointer;
  }
</style>
