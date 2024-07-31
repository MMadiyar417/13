<script setup>
import { ref } from 'vue';
import UserList from '@/components/UserList.vue';
import UserDetails from '@/components/UserDetails.vue';

const userList = ref([])
const selectedUser = ref(null);

   fetch('https://jsonplaceholder.typicode.com/users')
  .then((response) => response.json())
  .then((json) => userList.value = json)

const handleUserSelected = (user)=>{
  console.log(user);
  selectedUser.value = user
}

</script>

<template>
    <UserList :users="userList" @user-selected="handleUserSelected" />
    <UserDetails v-if="selectedUser" :user="selectedUser" />
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
