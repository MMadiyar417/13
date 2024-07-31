<script setup>
const props = defineProps ({
  users: Array,
})
</script>
<template>
  
    <ul  >
      <li v-for="user in users" @click="$emit('userSelected', user)">{{ user.username }}</li>
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
