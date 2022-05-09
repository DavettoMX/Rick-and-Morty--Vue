<template>
  <div>
    <h1>Rick & Morty</h1>
    <FilterByName />
    <FilterByStatus />
    <ListCharacters />
  </div>
</template>

<script>
import ListCharacters from "@/components/ListCharacters";
import FilterByStatus from "@/components/FilterByStatus";
import FilterByName from "@/components/FilterByName";

export default {
  name: "App",
  components: {
    ListCharacters,
    FilterByStatus,
    FilterByName
  },
};
</script>

<style lang="scss">
:root {
  --background-body: #24282f;
  --background-card: #3c3e44;
  --text-white: #ffffff;
  --text-gray: #828282;
  --text-orange: #ff9f1c;
}

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  background-color: var(--background-body);
  color: var(--text-white);
  font-family: "Helvetica Neue", sans-serif;
}

h1 {
  margin: 4rem;
  text-align: center;
  font-size: 3.5rem;
}

.container {
  width: 100%;
  max-width: 90%;
  margin: 0mm 5rem auto;
}

img {
  width: 100%;
}
</style>