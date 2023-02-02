<template>
    <div role="alert" class="rounded-xl border border-gray-100 p-4 shadow-xl max-w-sm bg-slate-800 mx-auto" v-show="successMsg || errMsg">
      <div class="flex items-start gap-4">
        <span class="text-green-600" v-show="successMsg">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="1.5"
            stroke="currentColor"
            class="h-6 w-6"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M9 12.75L11.25 15 15 9.75M21 12a9 9 0 11-18 0 9 9 0 0118 0z"
            />
          </svg>
        </span>
        <span class="text-red-600" v-show="errMsg">
         <Icon name="uil:exclamation-circle" class="h-6 w-6" />
        </span>
      

  
        <div class="flex-1">
          <strong class="block font-medium text-gray-50"> Status </strong>
  
          <p class="mt-1 text-sm text-gray-50" v-show="successMessage">{{ successMessage }}.</p>
          <p class="mt-1 text-sm text-gray-50" v-show="errorMessage">{{ errorMessage }}.</p>
        </div>
  
        <button class="text-gray-300 transition hover:text-gray-200" @click="close">
          <span class="sr-only">Dismiss popup</span>
  
          <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="1.5"
            stroke="currentColor"
            class="h-6 w-6"
          >
            <path stroke-linecap="round" stroke-linejoin="round" d="M6 18L18 6M6 6l12 12" />
          </svg>
        </button>
      </div>
    </div>
  </template>
  
  <script>
import { Icon } from '@iconify/vue';

  export default {
    props: ["successMessage", "errorMessage", "successMsg", "errMsg", "close"],
    setup(props, context) {
        const close = () => {
            context.emit("close");
        };
        return { close, ...toRefs(props) };
    },
    components: { Icon }
}
  </script>
  
  <style></style>