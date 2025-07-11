<template>
  <header class="bg-gradient-to-r from-blue-50 to-indigo-50 shadow-lg sticky top-0 z-50 backdrop-blur-sm bg-opacity-80 border-b border-gray-200">
    <nav class="container mx-auto px-6 py-3 flex justify-between items-center">
      <!-- Logo with name looping animation -->
      <div class="flex items-center space-x-2 overflow-hidden">
        <div class="w-8 h-8 bg-blue-500 rounded-full flex items-center justify-center text-white font-bold animate-bounce">N</div>
        <div class="overflow-hidden w-32 md:w-40">  <!-- Fixed width for name container -->
          <div class="text-2xl font-bold bg-gradient-to-r from-blue-600 to-indigo-600 bg-clip-text text-transparent whitespace-nowrap">
            <span class="inline-block animate-name-loop pl-[100%]">Nama Anda</span>
          </div>
        </div>
      </div>

      <!-- Navigation Links -->
      <ul class="hidden md:flex space-x-8">
        <li>
          <a href="#profil" class="relative text-gray-700 hover:text-blue-600 font-medium transition-colors duration-300 group">
            Profil
            <span class="absolute bottom-0 left-0 w-0 h-0.5 bg-blue-500 transition-all duration-300 group-hover:w-full"></span>
          </a>
        </li>
        <li>
          <a href="#pendidikan" class="relative text-gray-700 hover:text-blue-600 font-medium transition-colors duration-300 group">
            Pendidikan
            <span class="absolute bottom-0 left-0 w-0 h-0.5 bg-blue-500 transition-all duration-300 group-hover:w-full"></span>
          </a>
        </li>
        <li>
          <a href="#skill" class="relative text-gray-700 hover:text-blue-600 font-medium transition-colors duration-300 group">
            Skill
            <span class="absolute bottom-0 left-0 w-0 h-0.5 bg-blue-500 transition-all duration-300 group-hover:w-full"></span>
          </a>
        </li>
        <li>
          <a href="#proyek" class="relative text-gray-700 hover:text-blue-600 font-medium transition-colors duration-300 group">
            Proyek
            <span class="absolute bottom-0 left-0 w-0 h-0.5 bg-blue-500 transition-all duration-300 group-hover:w-full"></span>
          </a>
        </li>
        <li>
          <a href="#kontak" class="relative px-4 py-2 bg-blue-500 text-white rounded-lg hover:bg-blue-600 transition-colors duration-300 shadow-md hover:shadow-lg">
            Kontak
          </a>
        </li>
      </ul>

      <!-- Mobile menu button -->
      <button class="md:hidden text-gray-700 focus:outline-none">
        <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"></path>
        </svg>
      </button>
    </nav>
  </header>
</template>

<style>
  /* Smooth name looping animation */
  @keyframes nameLoop {
    0% { transform: translateX(0); }
    100% { transform: translateX(-100%); }
  }

  .animate-name-loop {
    animation: nameLoop 6s linear infinite;
    display: inline-block;
    padding-right: 100%; /* Creates space between loops */
  }

  .animate-bounce {
    animation: bounce 2s infinite;
  }

  @keyframes bounce {
    0%, 100% { transform: translateY(0); }
    50% { transform: translateY(-5px); }
  }
</style>
