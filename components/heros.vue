<template>
<main>
  <main>
    <!-- This example requires Tailwind CSS v2.0+ -->
    <div class="relative overflow-hidden bg-white ">
      <div class="mx-auto max-w-7xl">
        <div
          class="relative z-10 bg-white  pb-8 sm:pb-16 md:pb-20 lg:w-full lg:max-w-2xl lg:pb-28 xl:pb-32"
        >
         

          <div>
            <div class="relative px-4 pt-6 sm:px-6 lg:px-8  md:bg-transparent bg-slate-900">
              <nav
                class="relative flex items-center justify-between sm:h-10 lg:justify-start  py-3"
                aria-label="Global"
              >
                <div class="flex flex-shrink-0 flex-grow items-center lg:flex-grow-0">
                  <div class="flex w-full items-center justify-between md:w-auto">
                    <a href="#">
                      <!-- https://tailwindui.com/img/logos/mark.svg?color=indigo&shade=600 -->
                    </a>
                    <div class="-mr-2 flex items-center md:hidden ">
                    
                    </div>
                  </div>
                </div>
                <div class=" md:block md:space-x-8 md:pr-1 mx-auto flex flex-row flex-wrap justify-start items-start gap-x-3 Alegreya Sans font-family gap-y-3">
                  <NuxtLink
                    to="/"
                    class="  md:text-black text-white hover:text-orange-600 font-family"
                  >
                    <span
                      >
                      <Icon name="uil:home-alt" class="w-6 h-6" />
                      </span>
                    Home
                  </NuxtLink>
                  <a
                  target="_blank"
                    href="https://github.com/Francis-Mwaniki/food-restaurant-a.i/graphs/contributors"
                    class="  md:text-black text-white hover:text-orange-600"
                  >
                    <span
                      >
                      <Icon name="uil:github" class="w-6 h-6" />
                      </span>
                    collaborators
                  </a>
                 
                  
                  <Nuxt-link
                    to="/chatbot"
                    class="  md:text-black text-white hover:text-orange-600 font-family"
                  >
                    <span
                      >
                      <Icon name="fluent-emoji-high-contrast:robot" class="w-6 h-6" />
                      </span>
                   Chatbot
                  </Nuxt-link>
                  
                 
                  <Nuxt-link
                  to="/login"
                    class=" rounded-md border border-transparent md:h-14 bg-gradient-to-r from-slate-900 to-slate-900 px-4 md:py-3   text-orange-400 hover:bg-slate-700  font-family"
                    >
                    <span
                       class=" "> <Icon name="ic:round-login" class="w-6 h-6" /></span>
                    Log in
                  </Nuxt-link>
                </div>
                 
              </nav>
            </div>

            <!--
            Mobile menu, show/hide based on menu open state.
  
            Entering: "duration-150 ease-out"
              From: "opacity-0 scale-95"
              To: "opacity-100 scale-100"
            Leaving: "duration-100 ease-in"
              From: "opacity-100 scale-100"
              To: "opacity-0 scale-95"
          -->
          
          </div>

          <main
            class="mx-auto mt-10 max-w-7xl px-4 sm:mt-12 sm:px-6 md:mt-16 lg:mt-20 lg:px-8 xl:mt-28"
          >
            <div class="sm:text-center lg:text-left">
              <h1
                class="text-4xl  tracking-tight text-gray-900  sm:text-5xl md:text-6xl"
              >
                <span class="block xl:inline  md:text-5xl text-4xl">Discover magic recipes <span class=" text-orange-600 text-5xl">.</span> </span>
                <span class="block text-orange-600 xl:inline">
               <p class=""> Every meal every day!</p></span
                >
              </h1>
              <p
                class="mt-3 text-base text-gray-500 sm:mx-auto font-mono sm:mt-5 sm:max-w-xl sm:text-lg md:mt-5 md:text-xl lg:mx-0"
              >
              AI-generated recipes can help save time, reduce food waste, and provide new and innovative recipe ideas by quickly matching ingredients to thousands of existing recipes.
              </p>
              <div class="mt-5 sm:mt-8 sm:flex sm:justify-center lg:justify-start">
                <div class="rounded-md shadow">
                  <Nuxt-link
                    to=""
                    class=" flex  items-center justify-center rounded-md border border-transparent h-14 bg-gradient-to-r from-slate-900 to-slate-900 px-4 py-3 text-base   text-orange-400 hover:bg-slate-700 md:py-3 md:px-10 md:text-2xl"
                    >
                   
                    <NuxtLink to="/login" class=" ">Get started</NuxtLink>
                    <Icon name="ph:target" class=" h-6 w-6"/>
                  </Nuxt-link>
                </div>
               
              </div>
            </div>
          </main>
        </div>
      </div>
     
      <div class="lg:absolute lg:inset-y-0 lg:right-0 lg:w-1/2">
         <img
          class="h-96   w-full object-cover sm:h-72 md:h-96  lg:h-full lg:w-full rounded"
       src="https://cdn.pixabay.com/photo/2018/03/28/20/32/food-3270461__340.jpg"  
          alt=""
        /> 
      </div>
    </div>

    
  </main>
  
<div
  class=" bg-white relative flex flex-col-reverse px-4 py-16 mx-auto lg:block lg:flex-col lg:py-32 xl:py-48 md:px-8 sm:max-w-xl md:max-w-full"
>
  <div
    class="z-0 flex justify-center h-full -mx-4 overflow-hidden lg:pt-24 lg:pb-16 lg:pr-8 xl:pr-0 lg:w-1/2 lg:absolute lg:justify-end lg:bottom-0 lg:left-0 lg:items-center"
  >
    <img
      src="https://cdn.pixabay.com/photo/2017/09/19/20/19/pizza-2766471_960_720.jpg"
      class="object-cover object-right w-full h-auto lg:w-auto lg:h-full rounded"
      alt=""
    />
  </div>
  <div class="relative flex justify-end max-w-xl mx-auto xl:pr-32 lg:max-w-screen-xl">
    <div class="mb-16 lg:pr-5 lg:max-w-lg lg:mb-0">
      <div class="max-w-xl mb-6">
        <div>
          <p
            class="inline-block px-3 py-px mb-4 text-xs font-semibold tracking-wider text-teal-900  uppercase rounded-full bg-teal-accent-400"
          >
            
          </p>
        </div>
        <h2
          class="max-w-lg mb-2  text-lg md:text-4xl  tracking-tight text-orange-600  sm:text-4xl sm:leading-none ml-10"
        >
        AI GENERATED RECIPES.<br class="" />

          <span class="inline-block text-deep-purple-accent-400 "
            ></span
          >
        </h2>
        <p class="text-base text-gray-700  ml-10 md:text-lg">
          Recipes are more than just instructions, they are a way to preserve cultural traditions, share personal experiences and bring people together around a shared love of food.
        </p>
      </div>
    </div>
  </div>
</div>
</main>
<Foot/>

 
</template>

<script>
/* import Dropdown1 from "./Dropdown.vue"; */
 
export default {
  
  mounted() {
    this.donate = true;
  },
  data() {
    return {
      mode: false,
      donate: false,
      give: "donate",
    };
  },
  methods: {
    toggleMode() {
      this.mode = !this.mode;
    },
    Donate() {
      navigateTo("/Popup");
    },
  },
};
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Rubik:wght@600&display=swap');
font-family{
  font-family: 'Rubik', sans-serif;};
</style>
 
