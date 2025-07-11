<template>
  <header class="bg-gradient-to-r from-blue-50 to-indigo-50 shadow-lg sticky top-0 z-50 backdrop-blur-sm bg-opacity-80 border-b border-gray-200">
    <nav class="container mx-auto px-6 py-3 flex justify-between items-center">

      <div class="flex items-center space-x-2">
        <div class="w-8 h-8 bg-blue-500 rounded-full flex items-center justify-center text-white font-bold animate-bounce">S</div>
        <div class="text-2xl font-bold text-transparent bg-clip-text bg-gradient-to-r from-blue-600 to-indigo-600">
          <span class="typing-animation whitespace-nowrap"></span>
          <span class="typing-cursor">|</span>
        </div>
      </div>


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


      <button class="md:hidden text-gray-700 focus:outline-none">
        <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"></path>
        </svg>
      </button>
    </nav>
  </header>
</template>

<script>
export default {
  mounted() {
    this.typeText();
  },
  methods: {
    typeText() {
      const texts = ["Ilham Bintang Saputra", "Know As Bintang", "Or", "Star"];
      const typingElement = document.querySelector('.typing-animation');
      const cursorElement = document.querySelector('.typing-cursor');
      let textIndex = 0;
      let charIndex = 0;
      let isDeleting = false;
      let typingSpeed = 150;

      const type = () => {
        const currentText = texts[textIndex];

        if (isDeleting) {
          // Deleting text
          typingElement.textContent = currentText.substring(0, charIndex - 1);
          charIndex--;
          typingSpeed = 50;
        } else {
          // Typing text
          typingElement.textContent = currentText.substring(0, charIndex + 1);
          charIndex++;
          typingSpeed = 150;
        }


        cursorElement.style.opacity = cursorElement.style.opacity === '0' ? '1' : '0';


        if (!isDeleting && charIndex === currentText.length) {
          // Pause at end
          typingSpeed = 2000;
          isDeleting = true;
        } else if (isDeleting && charIndex === 0) {
          // Move to next text
          isDeleting = false;
          textIndex = (textIndex + 1) % texts.length;
          typingSpeed = 500;
        }

        setTimeout(type, typingSpeed);
      };

      type();
    }
  }
};
</script>

<style>
  .typing-cursor {
    display: inline-block;
    margin-left: 2px;
    animation: blink 0.7s infinite;
    color: #3b82f6;
  }

  @keyframes blink {
    0%, 100% { opacity: 1; }
    50% { opacity: 0; }
  }

  .animate-bounce {
    animation: bounce 2s infinite;
  }

  @keyframes bounce {
    0%, 100% { transform: translateY(0); }
    50% { transform: translateY(-5px); }
  }
</style>
