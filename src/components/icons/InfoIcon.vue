<template>
    <div class="relative inline-block">
      <svg 
        xmlns="http://www.w3.org/2000/svg"
        fill="none" 
        viewBox="0 0 24 24" 
        stroke-width="1.5" 
        stroke="currentColor"
        @mouseover="showTooltip = true"
        @mouseout="showTooltip = false"
        class="w-6 h-6 cursor-pointer">
        <path 
          stroke-linecap="round" 
          stroke-linejoin="round" 
          d="M11.25 11.25l.041-.02a.75.75 0 011.063.852l-.708 2.836a.75.75 0 001.063.853l.041-.021M21 12a9 9 0 11-18 0 9 9 0 0118 0zm-9-3.75h.008v.008H12V8.25z"
        />
      </svg>
      <div v-if="showTooltip" class="absolute z-10 left-1/2 transform -translate-x-1/2 mt-2 w-56 p-2 bg-gray-700 text-white rounded shadow-md">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit.
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: "InfoIcon",
    data() {
      return {
        showTooltip: false,
      };
    },
  };
  </script>
  
  <style scoped></style>
  