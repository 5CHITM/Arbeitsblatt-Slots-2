<template>
  <div class="container mt-5" id="app">
    <ShowFriends :friends="myFriends">
      <template v-slot:title>Meine Freunde</template>
      <template v-slot:row.name="{ item }">
        <span class="fw-bold text-primary"> {{ item.name }}</span>
      </template>
      <template v-slot:row.alter="{ item }">
        {{ item.alter }}
      </template>
    </ShowFriends>
  </div>
</template>


<script>
import ShowFriends from '@/components/ShowFriends.vue';

export default {
  name: 'App',
  components: {
    ShowFriends,
  },
  data() {
    return {
      myFriends: [
        { name: 'Jonah', alter: 37 },
        { name: 'Alena', alter: 28 },
        { name: 'Milos', alter: 45 },
      ],
    };
  },
};
</script>
