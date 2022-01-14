<template>
  <div>
    <h4 class="fw-bold mb-5">Scratchy Inc. feat. Lang</h4>
    <h4 class="fw-bold">Boss</h4>
    <slot name="boss" :item="boss"> </slot>
    <div class="mt-5">
      <h4 class="fw-bold">Employees</h4>
      <div class="d-flex flex-row">
        <slot name="employees" v-for="emp of employees" :item="emp"> </slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    cats: {
      type: Array,
    },
  },
  data() {
    return {
      boss: this.cats.find((el) => el.role == 'Boss'),
      employees: this.cats.filter((el) => el.role != 'Boss'),
    };
  },
};
</script>

<style lang="scss" scoped></style>
