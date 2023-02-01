<template>
     <div
      wire:isFetching
      v-show="isFetching"
      class="fixed top-0 left-0 right-0 bottom-0 w-full h-screen z-50 overflow-hidden bg-gray-900 opacity-75 flex flex-col items-center justify-center"
    >
      <h2 class="text-center dark:text-pink-300 text-indigo-100 text-xl font-semibold">
        <img src="../assets/img/ring.gif" class="bg-slate-900 w-20 h-20" alt="" />
      </h2>
      <p class="sm:w-1/3 w-2/3 text-center text-white text-2xl">it's Fetching.....</p>
      <ClientOnly>
        <button
          class="btn-3 ring-1 ring-white hover:bg-slate-800 bg-gray-900 rounded-lg"
          @click="isFetching = false"
        >
          Cancel
          <Icon name="ic:outline-cancel" />
        </button>
      </ClientOnly>
    </div>
  <div class="max-w-5xl mx-auto flex md:flex-row flex-col flex-wrap my-2 gap-y-2">
    <div class="" v-for="instruction in all_instructions[0]">
      <article class="rounded-xl bg-slate-800 p-6 sm:ring-1 ring-indigo-600 sm:p-8">
        <div class="flex items-start">
          <div
            class="hidden sm:grid sm:h-20 sm:w-20 sm:shrink-0 sm:place-content-center sm:rounded-full sm:border-2 sm:border-indigo-500"
            aria-hidden="true"
          >
            <div class="flex items-center gap-1">
              <span class="h-8 w-0.5 rounded-full bg-indigo-500"></span>
              <span class="h-6 w-0.5 rounded-full bg-indigo-500"></span>
              <span class="h-4 w-0.5 rounded-full bg-indigo-500"></span>
              <span class="h-6 w-0.5 rounded-full bg-indigo-500"></span>
              <span class="h-8 w-0.5 rounded-full bg-indigo-500"></span>
            </div>
          </div>

          <div class="sm:ml-8">
            <strong
              class="rounded border border-indigo-500 bg-indigo-500 px-3 py-1.5 text-[10px] font-medium text-white"
            >
              {{ instruction.id }}
            </strong>

            <h3 class="mt-4 text-lg font-medium sm:text-xl">
              <a href="" class="hover:underline"> Instructions #{{ instruction.id }} </a>
            </h3>

            <p class="mt-1 text-sm text-gray-50">
              {{ instruction.instructions }}
            </p>

            <div class="mt-4 sm:flex sm:items-center sm:gap-2">
              <div class="flex items-center text-gray-50">
                <svg
                  class="h-4 w-4"
                  fill="none"
                  stroke="currentColor"
                  viewBox="0 0 24 24"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    stroke-width="2"
                    d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z"
                  ></path>
                </svg>
                <p class="ml-1 text-xs font-medium">48:32 minutes</p>
              </div>

              <span class="hidden sm:block" aria-hidden="true">&middot;</span>

              <p class="mt-2 text-xs font-medium text-gray-500 sm:mt-0">
                Featuring <a href="" class="underline hover:text-gray-50">Barry</a>,
                <a href="" class="underline hover:text-gray-50">Sandra</a> and
                <a href="" class="underline hover:text-gray-50">August</a>
              </p>
            </div>
          </div>
        </div>
      </article>
    </div>
  </div>
</template>

<script>
export default {
  setup() {
    const client = useSupabaseClient();
    const all_instructions = ref([]);
    let isFetching = ref(false);
    const get_all = async () => {
      isFetching.value = true;
      const { data, error } = await client.from("recipes").select("*");
      if (data) {
        all_instructions.value.push(data);
        console.log(all_instructions.value);
      } else {
        alert("error in retrieving");
      }
    };
    setTimeout(() => {
            isFetching.value = false;
          }, 4000);
    get_all();
    return {
      get_all,
      isFetching,
      all_instructions,
    };
  },
};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Alegreya+Sans:wght@100;300;400;500;700;800;900&display=swap");

* {
  font-family: "Alegreya Sans", sans-serif;
}
 .btn-3 {
    padding: 10px 30px;
    color: white;
  }
  
</style>
