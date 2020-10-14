<template>
  <div class="income-list">
    <IncomeItem v-for="obj in state.sortedIncome" :key="obj.id" :income="obj" @remove-item="removeItem" />
  </div>
</template>

<script>
import IncomeItem from './IncomeItem';

export default {
  props: {
    state: Object
  },
  setup (props, { emit }) {
    function removeItem(id) {
      emit( 'remove-item', id );
    }

    return {
      IncomeItem,
      removeItem
    }
  }
}
</script>

<style scoped>
  .income-list {
    margin-top: 30px;
    padding: 15px;
  }
</style>