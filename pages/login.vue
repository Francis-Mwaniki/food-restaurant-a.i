<template>
    <div class="min-h-full flex flex-col justify-center  sm:px-6 lg:px-8">
      <div class="sm:mx-auto sm:w-full sm:max-w-md">
       
        <h2 class="mt-6 text-center text-3xl font-extrabold text-orange-600">
          Sign in to your account
        </h2>
      </div>
  
      <div class="mt-8 sm:mx-auto sm:w-full sm:max-w-md">
        <div class="bg-white py-8 px- shadow sm:rounded-lg sm:px-10">
          <vee-form
            class="space-y-6"
            action="#"
            method="POST"
            :validation-schema="loginSchema"
            @submit="login"
          >
            <div>
              <label for="email" class="block text-lg font-bold text-gray-700">
                Email address
              </label>
              <div class="mt-1">
                <input
                  id="email"
                  name="email"
                  type="email"
                  autocomplete="email"
                  class="appearance-none block w-full px-6 py-4 border border-gray-300 rounded-md shadow-sm placeholder-gray-400 focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm"
                />
                <ErrorMessage class="text-red-500" name="email" />
              </div>
            </div>
  
            <div>
              <label for="password" class="block text-lg font-bold text-gray-700">
                Password
              </label>
              <div class="mt-1">
                <input
                  id="password"
                  name="password"
                  type="password"
                  autocomplete="current-password"
                  class="appearance-none block w-full px-3 py-4 border border-gray-300 rounded-md shadow-sm placeholder-gray-400 focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm"
                />
                <ErrorMessage class="text-red-500" name="password" />
              </div>
            </div>
        
  
            <div class="flex items-center justify-start">
              <div class="text-sm">
                <a href="#" class="font-bold text-lg text-orange-600 hover:text-black">
                  Forgot your password?
                </a>
              </div>
            </div>
  
            <div>
              <button
                type="submit"
                class="w-full flex justify-center py-2 px-4 border border-transparent rounded-md shadow-sm text-sm font-bold text-orange-500 bg-black hover:bg-slate-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500"
                :class="[login_in_submission ? 'bg-gray-400 hover:bg-slate-400' : '']"
                :disabled="login_in_submission"
              >
                <svg
                  v-if="login_show_alert"
                  class="animate-spin -ml-1 mr-3 h-5 w-5 text-white"
                  xmlns="http://www.w3.org/2000/svg"
                  fill="none"
                  viewBox="0 0 24 24"
                >
                  <circle
                    class="opacity-25"
                    cx="12"
                    cy="12"
                    r="10"
                    stroke="currentColor"
                    stroke-width="4"
                  ></circle>
                  <path
                    class="opacity-75"
                    fill="currentColor"
                    d="M4 12a8 8 0 018-8V0C5.373 0 0 5.373 0 12h4zm2 5.291A7.962 7.962 0 014 12H0c0 3.042 1.135 5.824 3 7.938l3-2.647z"
                  ></path>
                </svg>
                {{ login_show_alert ? "Logging..." : "Sign In" }}
              </button>
            </div>
          </vee-form>
  
          <div class="mt-6">
            <div class="relative">
              <div class="absolute inset-0 flex items-center">
                <div class="w-full border-t border-gray-300" />
              </div>
              <div class="relative flex justify-center text-sm">
                <span class="px-2 text-lg bg-white text-black"> Don't have an account? </span>
              </div>
            </div>
  
            <router-link
              to="/Signup"
              class="w-full inline-flex justify-center text-lg font-bold text-orange-600 cursor-pointer"
            >
              Register
            </router-link>
            <div class="mt-6"></div>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: "LoginForm",
  
    data() {
      return {
        loginSchema: {
          email: "required|min:3|max:100|email",
          password: "required|min:8|max:32",
        },
  
        login_in_submission: false,
        login_show_alert: false,
      };
    },
    methods: {
      login(values) {
        this.login_in_submission = true;
        this.login_show_alert = true;
        console.log(values);
      },
    },
  };
  </script>
  