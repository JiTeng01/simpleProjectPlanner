<template>
  <nav class="filter-nav">
      <button @click="updateFilter('all')" :class="{active: currentStatus === 'all'}">View All</button>
      <button @click="updateFilter('completed')" :class="{active: currentStatus === 'completed'}">Completed</button>
      <button @click="updateFilter('pending')" :class="{active: currentStatus === 'pending'}">Pending</button>
  </nav>
</template>

<script>
export default {
    props: ['currentStatus'],
    methods: {
        updateFilter(status) {
            this.$emit('filterChange', status)
        }
    }
}
</script>

<style>
.filter-nav button {
    background: none;
    border: none;
    color: #bbb;
    outline: none;
    font-size: 12px;
    text-transform: uppercase;
    margin-right: 10px;
    letter-spacing: 1px;
    font-weight: bold;
    cursor: pointer;
}
.filter-nav button.active {
    color: #555;
}
</style>