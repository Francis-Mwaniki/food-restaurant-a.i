<template>
  <div>
    <Navbar :openSearch="openSearch" :searchStatus="searchStatus" :search="search" :query="query" />
    <Instructions />
  </div>
</template>

<script >
export default {
  setup() {
    const searchStatus = ref(false);
    let query = ref("");
    const openSearch = () => {
      searchStatus.value = !searchStatus.value;
    };
    const search=()=>{
     query.value=query.value
    }
  
    return {
      openSearch,
      query,
      searchStatus,
      search,
    };
  },
}
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Alegreya+Sans:wght@100;300;400;500;700;800;900&display=swap");

* {
  font-family: "Alegreya Sans", sans-serif;
}
</style>
