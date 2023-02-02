<template>
  <div>
    <div class="navbar bg-slate-900">
      <div class="navbar-start">
        <div class="dropdown">
          <label tabindex="0" class="btn btn-ghost btn-circle">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="h-5 w-5"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M4 6h16M4 12h16M4 18h7"
              />
            </svg>
          </label>
          <ul
            tabindex="0"
            class="menu menu-compact dropdown-content mt-3 p-2 shadow bg-slate-800 rounded-box w-52"
          >
            <li><NuxtLink to="/chatbot">Chatbot</NuxtLink></li>
            <li><NuxtLink to="/login">Login</NuxtLink></li>
            <li><NuxtLink to="/">Home</NuxtLink></li>
          </ul>
        </div>
      </div>
      <div class="navbar-center">
        <a class="btn btn-ghost normal-case text-xl">Instructions(commands)</a>
      </div>
      <div class="navbar-end">
        <button class="btn btn-ghost btn-circle" @click="openSearch">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            class="h-5 w-5"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z"
            />
          </svg>
        </button>
       
       
      </div>
    </div>
    <div class=" flex justify-center items-center mx-auto  my-2" v-show="searchStatus">
         <input type="query" name="" @keydown.enter="search(q)"  class=" py-3 px-7 bg-slate-800 ring-1 ring-indigo-700 text-white rounded" id="">
        </div>
  </div>
  
</template>

<script>
export default {
  props: ["openSearch",'search','query',"searchStatus"],
    setup(props, context) {

        const openSearch = () => {
            context.emit("openSearch");
        };
       
        return { openSearch, ...toRefs(props)};
    },
    
};

</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Alegreya+Sans:wght@100;300;400;500;700;800;900&display=swap");

* {
  font-family: "Alegreya Sans", sans-serif;
}
</style>
