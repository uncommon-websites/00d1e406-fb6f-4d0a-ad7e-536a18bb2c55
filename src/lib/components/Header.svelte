<script>
  import { onMount } from 'svelte';

  let isScrolled = false;

  onMount(() => {
    const handleScroll = () => {
      isScrolled = window.scrollY > 10;
    };
    window.addEventListener('scroll', handleScroll);
    return () => window.removeEventListener('scroll', handleScroll);
  });
</script>

<header class="fixed top-0 left-0 right-0 z-50 transition-all duration-300 px-6 py-5 flex items-center justify-between {isScrolled ? 'bg-[#F9F8F6]/90 backdrop-blur-md shadow-sm' : 'bg-transparent'}">
  <div class="flex items-center">
    <!-- Logo -->
    <a href="/" class="flex items-center gap-2 group">
      <svg width="24" height="26" viewBox="0 0 91 100" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path fill-rule="evenodd" clip-rule="evenodd" d="M38.5213 0H71.8426L50.2602 28.5752H90.6904L19.0338 100L40.8851 51.8383H0.69043L38.5213 0Z" fill="black"/>
      </svg>
      <span class="font-bold text-xl tracking-wide text-[#1A1A1A]">Delphi</span>
    </a>
  </div>

  <div class="flex items-center gap-8">
    <nav class="hidden md:flex items-center gap-8 text-[13px] font-medium text-gray-600">
      <a href="#features" class="hover:text-black transition-colors">Features</a>
      <a href="#faq" class="hover:text-black transition-colors">FAQ</a>
    </nav>
    <a href="#join" class="bg-[#1A1A1A] text-white text-[13px] font-medium px-5 py-2.5 rounded-sm hover:bg-black transition-colors">
      Get Started
    </a>
  </div>
</header>