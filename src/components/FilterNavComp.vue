<template>
  <nav class="filter-nav">
    <button @click="updateFilter('all')" :class="{active: current === 'all'}">All</button>
    <button @click="updateFilter('completed')" :class="{active: current === 'completed'}">Completed</button>
    <button @click="updateFilter('ongoing')" :class="{active: current === 'ongoing'}">Ongoing</button>
  </nav>
</template>

<script>
export default {
  props: ['current'],
  methods: {
    updateFilter(data) {
      this.$emit('filterChange', data)
    }
  },
}
</script>

<style>
  .filter-nav button {
    background: transparent;
    border: none;
    color: #777777ab;
    outline: none;
    font-size: 14px;
    text-transform: uppercase;
    margin-right: 10px;
    letter-spacing: 1px;
    font-weight: bold;
    cursor: pointer;
  }
  .filter-nav button.active {
    color: #333;
  }
</style>