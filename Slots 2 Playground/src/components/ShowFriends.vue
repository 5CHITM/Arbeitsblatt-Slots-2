<template>
  <div>
    <h3>
      <slot name="title"> </slot>
    </h3>
    <table class="table">
      <tr v-for="(friend, i) of friends" :key="i">
        <td>
          <slot name="row.name" :item="friend"> </slot>
        </td>
        <td>
          <slot name="row.alter" :item="friend"> </slot>
        </td>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  props: {
    friends: {
      type: Array,
    },
  },
};
</script>
