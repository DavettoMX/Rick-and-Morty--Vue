<template>
  <div class="filter">
      <div class="item" @click="filter('')">
          All
      </div>
      <div class="item" @click="filter('Alive')">
          Alive
      </div>
      <div class="item" @click="filter('Dead')">
          Dead
      </div>
      <div class="item" @click="filter('unknown')">
          Unknown
      </div>
  </div>
</template>

<script>
import { useStore } from 'vuex'

export default {
    setup() {
        const store = useStore()

        const filter = ((status) => {
            store.dispatch('filterByStatus', status);
        })

        return {
            filter,
        }
    }
}
</script>

<style lang="scss">
.filter {
    width: 500px;
    margin: 3em auto;
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    border-radius: 10px;
    overflow: hidden;

    .item {
        padding: 1.5rem 0.5rem;
        background-color: var(--background-card);
        text-align: center;
        cursor: pointer;
        &:hover {
            background-color: var(--text-orange);
        }
    }
}
</style>