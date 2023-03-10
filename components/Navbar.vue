<template>
  <div
    class="w-full p-10 mx-auto flex md:flex-row flex-col md:justify-between justify-center absolute top-0 z-50"
  >
    <div
      class="flex gap-10 md:w-1/2 items-center w-full justify-center md:justify-start"
    >
      <NuxtLink to="/" class="text-white font-bold">Welcome</NuxtLink>
      <NuxtLink to="/register" class="text-white font-bold">Register</NuxtLink>
    </div>
    <div
      class="md:w-1/2 w-full flex md:justify-end items-center justify-center md:mt-0 mt-5"
    >
      <NuxtLink to="/" class="text-white font-bold">Login</NuxtLink>
      <button class="w-fit bg-red-700 rounded-2xl text-white h-10 ml-5 p-1">
        Get Started
      </button>
    </div>
  </div>
</template>

<script></script>
