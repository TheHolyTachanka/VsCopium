<template>
  <div class="relative min-h-screen md:flex">
<!--   mobile menu bar -->
  <div class='bg-gray-800 text-gray-100 flex justify-between md:hidden'>
<!--     logo -->
    <a href="" class="block p-4 text-white font-bold">Better Dev</a>
<!--     mobile menu botton -->
    <button class='mobile-menu-btn p-4 focus:bg-gray-700'>
      <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"></path></svg>
    </button>
  </div>
<!--   sidebar -->
  <div class='sidebar bg-blue-800 text-blue-100 w-64 space-y-6 px-2 py-7 absolute inset-y-0 left-0 transform -translate-x-full md:relative md:translate-x-0 transition duration-200 ease-in-out'>
<!--     logo -->
    <a href="#" class='px-4 text-white flex items-center space-x-2'>
      <svg class="w-8 h-8" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z"></path></svg>
    <span class="text-2xl font-extrabold">Better Dev</span>
    </a>
<!--     nav -->
    <nav>
      <a href="#" class="block py-2.5 px-4 hover:bg-blue-700 rounded hover:text-white">Home</a>
      <a href="#" class="block py-2.5 px-4 hover:bg-blue-700 rounded hover:text-white">About</a>
      <a href="#" class="block py-2.5 px-4 hover:bg-blue-700 rounded hover:text-white">features</a>
      <a href="#" class="block py-2.5 px-4 hover:bg-blue-700 rounded hover:text-white">Pricing</a>
    </nav>
  </div>
  
<!--   content -->
  <div class='flex-1 p-10 text-2xl font-bold'>
    content goes here
  </div>
</div>
</template>

<script>
// grab everything we need 
const btn = document.querySelector('.mobile-menu-btn')
const sidebar = document.querySelector('.sidebar')
// add out event listener for the click

btn.addEventListener('click',()=>{
  sidebar.classList.toggle('-translate-x-full')
})
</script>

<style>

</style>