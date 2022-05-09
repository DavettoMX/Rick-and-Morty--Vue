<template>
  <div class="search">
    <input
      type="text"
      placeholder="Search By Name"
      v-model="name"
      @keyup="filter()"
    />
  </div>
</template>

<script>
import { ref } from "vue";
import { useStore } from "vuex";
export default {
  setup() {
    const store = useStore();
    const name = ref("");
    const filter = () => {
      store.dispatch("filterByName", name.value);
    };

    return { name, filter };
  },
};
</script>

<style lang="scss">
.search {
  width: 20%;
  margin: 3rem auto 0;

  input {
    width: 100%;
    height: 3rem;
    border: none;
    border-radius: 10px;
    padding: 0 0.5rem;
    background-color: #3c3e44;
    color: #fff;

    &:focus {
      outline: none;
      background-color: #fff;
      color: #3c3e44;
    }
  }
}
</style>