<script lang="ts">
  import Header from "$lib/components/Header.svelte";
  
  // Icons
  const ArrowRight = `<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M5 12h14"/><path d="m12 5 7 7-7 7"/></svg>`;
  const PlayCircle = `<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="10"/><polygon points="10 8 16 12 10 16 10 8"/></svg>`;
  const ChevronLeft = `<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="m15 18-6-6 6-6"/></svg>`;
  const ChevronRight = `<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="m9 18 6-6-6-6"/></svg>`;
  const Check = `<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"><path d="M20 6 9 17l-5-5"/></svg>`;
  const Plus = `<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M5 12h14"/><path d="M12 5v14"/></svg>`;
  const Instagram = `<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect width="20" height="20" x="2" y="2" rx="5" ry="5"/><path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"/><line x1="17.5" x2="17.51" y1="6.5" y2="6.5"/></svg>`;
  const LinkedIn = `<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"/><rect width="4" height="12" x="2" y="9"/><circle cx="4" cy="4" r="2"/></svg>`;
  const XIcon = `<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M18 6 6 18"/><path d="m6 6 18 12"/></svg>`;

  // Data
  const heroImages = [
    "/generated/image-professional-podcast-host-speaking-into--1765401778539-0.webp",
    "/generated/image-confident-business-executive-giving-pres-1765401781495-1.webp",
    "/generated/image-author-writing-at-desk-with-books-and-la-1765401783672-2.webp",
    "/generated/image-content-creator-recording-video-in-home--1765401785991-3.webp",
    "/generated/image-coach-mentoring-client-in-bright-modern--1765401788424-4.webp",
    "/generated/image-entrepreneur-working-on-laptop-in-creati-1765401790727-5.webp"
  ];

  const benefitCards = [
    {
      title: "Deploy everywhere.",
      desc: "Your Digital Mind works across SMS, WhatsApp, Slack, websites, voice, video, and phone calls.",
      image: "/generated/image-person-using-smartphone-with-messaging-i-1765401793109-6.webp"
    },
    {
      title: "Your authentic voice.",
      desc: "Advanced voice synthesis captures your tone, style, and knowledge to create truly personalized interactions.",
      image: "/generated/image-professional-recording-audio-content-wit-1765401795456-7.webp"
    },
    {
      title: "Train with your content.",
      desc: "Upload text, audio, video or link to live feeds. Delphi indexes everything to mirror your expertise.",
      image: "/generated/image-person-organizing-digital-content-on-mul-1765401797639-8.webp"
    }
  ];

  const steps = [
    {
      step: 1,
      title: "Connect your content.",
      desc: "Upload or link your existing content—text, audio, video, podcasts, articles, or live feeds. Delphi makes it easy to get started.",
      image: "plan"
    },
    {
      step: 2,
      title: "Train your Digital Mind.",
      desc: "Our system automatically indexes your content and learns your unique style, tone, and expertise. Customize behavior with simple notes.",
      image: "schedule"
    },
    {
      step: 3,
      title: "Review and refine.",
      desc: "Test your Digital Mind, see how it responds, and make adjustments. You maintain complete control over what it says and how it sounds.",
      image: "results"
    },
    {
      step: 4,
      title: "Deploy across channels.",
      desc: "Share your Digital Mind via SMS, WhatsApp, Slack, your website, or even voice and video calls. One AI, infinite reach.",
      image: "notes"
    },
    {
      step: 5,
      title: "Scale your engagement.",
      desc: "Your Digital Mind handles unlimited conversations while you focus on what matters. Keep every relationship alive, automatically.",
      image: "improve"
    }
  ];

  const faqs = [
    "How does Delphi train on my content?",
    "Is Delphi right for me?",
    "How does voice cloning work?",
    "Can I control what my Digital Mind says?",
    "Where can I deploy my Digital Mind?"
  ];
</script>

<Header />

<main class="w-full overflow-x-hidden">
  <!-- Hero Section -->
  <section class="pt-32 pb-16 md:pt-40 md:pb-24 px-6 text-center max-w-7xl mx-auto">
    <h1 class="text-4xl md:text-6xl lg:text-7xl font-medium tracking-tight text-[#1A1A1A] mb-6 leading-[1.1]">
      Clone your expertise.<br />Scale your influence.
    </h1>
    <p class="text-gray-600 text-lg md:text-xl max-w-3xl mx-auto mb-10 leading-relaxed font-light">
      Turn your knowledge into a conversational AI that speaks with your voice, thinks like you, and engages your audience 24/7 across every channel.
    </p>
    <button class="bg-[#1A1A1A] text-white px-8 py-3.5 rounded-sm font-medium hover:bg-black transition-colors">
      Create Your Digital Mind
    </button>
  </section>

  <!-- Hero Images Scroll -->
  <div class="w-full overflow-x-auto pb-12 hide-scrollbar">
    <div class="flex gap-4 px-6 min-w-max">
      {#each heroImages as img, i}
        <div class="relative w-48 h-64 md:w-64 md:h-80 rounded-3xl overflow-hidden flex-shrink-0">
          <img src={img} alt="Thought Leaders" class="w-full h-full object-cover" />
        </div>
      {/each}
    </div>
  </div>

  <!-- App Feature Section -->
  <section class="py-20 px-6 max-w-7xl mx-auto" id="features">
    <div class="bg-white rounded-[40px] p-8 md:p-16 flex flex-col md:flex-row items-center gap-12 shadow-sm">
      <!-- Phone Mockup -->
      <div class="w-full md:w-1/2 flex justify-center">
        <div class="relative w-[280px] h-[580px] bg-black rounded-[40px] border-[8px] border-black shadow-2xl overflow-hidden">
          <div class="absolute top-0 left-0 right-0 h-6 bg-black z-20 flex justify-center">
            <div class="w-20 h-4 bg-black rounded-b-xl"></div>
          </div>
          <div class="w-full h-full bg-white pt-10 px-4 overflow-hidden flex flex-col">
            <!-- Mock Chat UI -->
            <div class="flex justify-between items-center mb-6">
              <div class="flex items-center gap-2">
                <div class="w-8 h-8 rounded-full bg-primary-500"></div>
                <div>
                  <div class="text-xs font-medium">Your Digital Mind</div>
                  <div class="text-[10px] text-gray-400">Active</div>
                </div>
              </div>
              <div class="w-6 h-6 rounded-full bg-gray-100"></div>
            </div>
            <div class="space-y-3 flex-1 overflow-hidden">
              <div class="bg-gray-100 p-3 rounded-2xl rounded-tl-sm text-xs max-w-[85%]">
                How do you balance art and business in music?
              </div>
              <div class="bg-primary-500 text-white p-3 rounded-2xl rounded-tr-sm text-xs ml-auto max-w-[85%]">
                It's about staying true to your creative vision while understanding the business side. I've learned that authenticity actually drives commercial success...
              </div>
              <div class="bg-gray-100 p-3 rounded-2xl rounded-tl-sm text-xs max-w-[85%]">
                What's your advice for new creators?
              </div>
              <div class="bg-primary-500 text-white p-3 rounded-2xl rounded-tr-sm text-xs ml-auto max-w-[85%]">
                Start with your unique voice. Don't try to copy what's trending. Build genuine connections...
              </div>
            </div>
            <div class="mt-4 flex items-center gap-2 p-2 bg-gray-50 rounded-full">
              <div class="flex-1 h-8 flex items-center px-3 text-[10px] text-gray-400">Type your question...</div>
              <div class="w-8 h-8 rounded-full bg-black"></div>
            </div>
          </div>
        </div>
      </div>
      
      <!-- Content -->
      <div class="w-full md:w-1/2 space-y-8">
        <h2 class="text-3xl md:text-4xl font-medium leading-tight text-[#1A1A1A]">
          Conversations that feel real.<br />
          Your Digital Mind speaks with your authentic voice, shares your knowledge, and maintains your unique perspective in every interaction.
        </h2>
        <div class="flex items-center justify-between pt-4">
          <button class="flex items-center gap-2 text-[#1A1A1A] font-medium hover:opacity-70 transition-opacity">
            {@html PlayCircle}
            See it in action
          </button>
          <div class="flex gap-2">
            <button class="p-2 rounded-full border border-gray-200 hover:bg-gray-50 text-gray-400 hover:text-black transition-colors">
              {@html ChevronLeft}
            </button>
            <button class="p-2 rounded-full border border-gray-200 hover:bg-gray-50 text-gray-400 hover:text-black transition-colors">
              {@html ChevronRight}
            </button>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Value Proposition -->
  <section class="py-16 px-6 max-w-7xl mx-auto">
    <div class="grid md:grid-cols-2 gap-12 items-start">
      <h2 class="text-3xl md:text-5xl font-medium tracking-tight text-[#1A1A1A] leading-tight">
        Never repeat yourself again.
      </h2>
      <p class="text-gray-600 text-lg font-light leading-relaxed">
        Your expertise is valuable. Your time is limited. Delphi lets you scale personal engagement without sacrificing authenticity. Keep every relationship alive, answer every question, and maintain your influence—all while focusing on what matters most.
      </p>
    </div>
  </section>

  <!-- Benefit Cards -->
  <section class="py-8 px-6 max-w-7xl mx-auto">
    <div class="grid md:grid-cols-3 gap-6">
      {#each benefitCards as card}
        <div class="relative h-[480px] rounded-3xl overflow-hidden group">
          <img src={card.image} alt={card.title} class="absolute inset-0 w-full h-full object-cover transition-transform duration-700 group-hover:scale-105" />
          <div class="absolute inset-0 bg-gradient-to-t from-black/60 via-black/20 to-transparent"></div>
          <div class="absolute bottom-0 left-0 right-0 p-8 text-white">
            <h3 class="text-2xl font-medium mb-3">{card.title}</h3>
            <p class="text-white/80 text-sm leading-relaxed font-light">{card.desc}</p>
          </div>
        </div>
      {/each}
    </div>
  </section>

  <!-- Testimonial -->
  <section class="py-24 px-6 max-w-4xl mx-auto text-center">
    <blockquote class="text-2xl md:text-3xl font-medium leading-relaxed text-[#1A1A1A] mb-8">
      "Delphi lets me scale my impact in a way I never thought possible. It's like having a version of myself that can help thousands of people simultaneously, while maintaining the authentic voice and insights that took me decades to develop."
    </blockquote>
    <div class="flex flex-col items-center gap-3">
      <img src="/generated/image-brian-halligan-mature-professional-busin-1765401799917-9.webp" alt="Brian Halligan" class="w-12 h-12 rounded-full object-cover" />
      <div class="text-center">
        <div class="font-medium text-sm">Brian Halligan</div>
        <div class="text-gray-500 text-xs">Co-founder of HubSpot</div>
      </div>
    </div>
  </section>

  <!-- Stats Grid -->
  <section class="py-12 px-6 max-w-7xl mx-auto border-t border-gray-200">
    <div class="grid md:grid-cols-3 gap-8 text-center md:text-left">
      <div>
        <h3 class="text-xl font-medium mb-2">Minutes to set up.</h3>
        <p class="text-gray-500 text-sm font-light">Upload your content or link to existing sources. Your Digital Mind starts learning immediately.</p>
      </div>
      <div>
        <h3 class="text-xl font-medium mb-2">Unlimited conversations.</h3>
        <p class="text-gray-500 text-sm font-light">Scale to 100M interactions. Your Digital Mind never gets tired, never forgets, always available.</p>
      </div>
      <div>
        <h3 class="text-xl font-medium mb-2">Deploy everywhere.</h3>
        <p class="text-gray-500 text-sm font-light">SMS, WhatsApp, Slack, web, voice, video. One Digital Mind, infinite reach across all channels.</p>
      </div>
    </div>
  </section>

  <!-- How it works -->
  <section class="py-20 px-6 max-w-7xl mx-auto">
    <div class="mb-16 max-w-md">
      <h2 class="text-4xl font-medium mb-6">How it works.</h2>
      <p class="text-gray-600 font-light">From content upload to deployment, Delphi makes it simple to create your Digital Mind. Train it on your expertise, customize its behavior, and deploy it across every channel where your audience needs you.</p>
    </div>

    <div class="space-y-6">
      {#each steps as step}
        <div class="bg-white rounded-[40px] p-8 md:p-12 flex flex-col items-center text-center max-w-2xl mx-auto shadow-sm">
          <div class="w-full text-left mb-8">
            <span class="inline-block w-8 h-8 rounded-full border border-gray-200 text-center leading-8 text-sm font-medium mb-4">{step.step}</span>
            <h3 class="text-2xl font-medium mb-3">{step.title}</h3>
            <p class="text-gray-500 font-light text-sm max-w-lg">{step.desc}</p>
          </div>
          
          <!-- Phone Mockup for Step -->
          <div class="relative w-[240px] h-[480px] bg-black rounded-[35px] border-[6px] border-black shadow-xl overflow-hidden mt-4">
             <div class="absolute top-0 left-0 right-0 h-5 bg-black z-20 flex justify-center">
                <div class="w-16 h-3 bg-black rounded-b-lg"></div>
             </div>
             <div class="w-full h-full bg-white pt-8 px-3 overflow-hidden">
                <!-- Dynamic Content based on step -->
                {#if step.image === 'plan'}
                  <div class="space-y-3 mt-4">
                    <div class="p-3 border rounded-xl border-black bg-gray-50">
                      <div class="font-bold text-xs mb-1">Optimal ID</div>
                      <div class="h-1 w-full bg-gray-200 rounded"></div>
                    </div>
                    <div class="p-3 border rounded-xl border-gray-200">
                       <div class="font-bold text-xs mb-1 text-gray-400">Essential</div>
                       <div class="h-1 w-full bg-gray-100 rounded"></div>
                    </div>
                  </div>
                {:else if step.image === 'schedule'}
                   <div class="mt-4">
                     <div class="text-center font-bold mb-4">Appointment</div>
                     <div class="bg-gray-100 h-32 rounded-xl mb-3 flex items-center justify-center text-xs text-gray-400">Map View</div>
                     <button class="w-full bg-black text-white text-xs py-2 rounded-lg">Confirm</button>
                   </div>
                {:else if step.image === 'results'}
                   <div class="bg-black h-full -mx-3 -mt-8 pt-10 px-3 text-white">
                      <div class="text-center mb-6">
                        <div class="w-12 h-12 bg-gray-700 rounded-full mx-auto mb-2"></div>
                        <div class="text-sm font-bold">Grace Parker</div>
                      </div>
                      <div class="space-y-2">
                         <div class="bg-gray-800 p-2 rounded-lg h-10"></div>
                         <div class="bg-gray-800 p-2 rounded-lg h-10"></div>
                      </div>
                   </div>
                {:else if step.image === 'notes'}
                   <div class="mt-4 space-y-3">
                      <div class="font-bold text-sm">Health Status</div>
                      <div class="text-[10px] text-gray-500 leading-relaxed">
                        You usually make smart choices for your health through regular exercise...
                      </div>
                      <div class="bg-gray-50 p-2 rounded text-[10px] text-gray-600">
                        Since your diet lacks enough fruits and vegetables...
                      </div>
                   </div>
                {:else}
                   <div class="mt-4 flex flex-col h-full">
                      <div class="flex-1">
                        <div class="bg-gray-100 p-2 rounded-lg rounded-tl-none text-[10px] mb-2 max-w-[80%]">
                          What benefits can I get by bringing ApoB closer to the optimal range?
                        </div>
                        <div class="bg-blue-50 p-2 rounded-lg rounded-tr-none text-[10px] ml-auto max-w-[80%]">
                          By lowering ApoB, you reduce the number of cholesterol-carrying particles...
                        </div>
                      </div>
                      <div class="h-10 border-t mt-2"></div>
                   </div>
                {/if}
             </div>
          </div>
        </div>
      {/each}
    </div>
  </section>

  <!-- Dark Cards Section -->
  <section class="py-8 px-6 max-w-7xl mx-auto">
    <div class="grid md:grid-cols-2 gap-6">
      <!-- Authenticity Card -->
      <div class="bg-[#111] rounded-[40px] p-8 md:p-12 text-white min-h-[500px] flex flex-col relative overflow-hidden">
        <div class="relative z-10">
          <h3 class="text-sm font-medium text-gray-400 mb-2">Your authentic voice.</h3>
          <h2 class="text-2xl md:text-3xl font-medium max-w-xs">Your Digital Mind only speaks your words, never improvises.</h2>
        </div>
        <!-- Lightning Visual -->
        <div class="absolute inset-0 flex items-center justify-center opacity-10 mt-20">
           <svg width="200" height="220" viewBox="0 0 91 100" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path fill-rule="evenodd" clip-rule="evenodd" d="M38.5213 0H71.8426L50.2602 28.5752H90.6904L19.0338 100L40.8851 51.8383H0.69043L38.5213 0Z" fill="white"/>
           </svg>
        </div>
      </div>

      <!-- Privacy Card -->
      <div class="bg-[#111] rounded-[40px] p-8 md:p-12 text-white min-h-[500px] flex flex-col relative overflow-hidden">
        <div class="relative z-10">
          <h3 class="text-sm font-medium text-gray-400 mb-2">Your data is safe with us.</h3>
          <h2 class="text-2xl md:text-3xl font-medium max-w-xs">Fully encrypted. Never shared. You maintain complete ownership.</h2>
        </div>
        <!-- Blurred Text Visual -->
        <div class="absolute inset-0 flex items-center justify-center mt-20 overflow-hidden">
           <div class="text-4xl font-mono text-gray-600 opacity-20 blur-sm select-none break-all p-8">
             Cont|%nt$9yT Knowl|I7dge Voic|&5e! Exper|?tise_Lw
           </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Pricing Section -->
  <section class="py-24 px-6 max-w-7xl mx-auto" id="join">
    <div class="text-center mb-16">
      <h2 class="text-3xl md:text-4xl font-medium mb-4">Scale your expertise.</h2>
      <p class="text-gray-500 font-light max-w-2xl mx-auto">From individual creators to world-class leaders, Delphi helps you clone your expertise and scale personal engagement across unlimited conversations.</p>
    </div>

    <div class="grid md:grid-cols-2 gap-6 max-w-4xl mx-auto">
      <!-- Creator Plan -->
      <div class="bg-white rounded-[32px] p-8 flex flex-col">
        <div class="w-12 h-12 bg-gray-100 rounded-full mb-6 flex items-center justify-center">
          <svg width="20" height="22" viewBox="0 0 91 100" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path fill-rule="evenodd" clip-rule="evenodd" d="M38.5213 0H71.8426L50.2602 28.5752H90.6904L19.0338 100L40.8851 51.8383H0.69043L38.5213 0Z" fill="black"/>
          </svg>
        </div>
        <h3 class="text-2xl font-medium mb-1">Creator</h3>
        <p class="text-sm text-gray-500 mb-6">For experts and creators.</p>
        <div class="mb-8">
          <span class="text-2xl font-medium">Custom pricing</span>
          <div class="text-[10px] text-gray-500 mt-1 font-medium">Starting at $99/month</div>
        </div>
        <ul class="space-y-4 mb-8 flex-1">
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Train on unlimited content from text, audio, and video sources.
          </li>
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Deploy across SMS, WhatsApp, Slack, and web.
          </li>
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Voice synthesis to match your authentic tone and style.
          </li>
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Analytics and conversation insights.
          </li>
        </ul>
        <button class="w-full bg-[#1A1A1A] text-white py-3 rounded-sm font-medium hover:bg-black transition-colors">Get Started</button>
      </div>

      <!-- Immortal Plan -->
      <div class="bg-white rounded-[32px] p-8 flex flex-col relative overflow-hidden">
        <div class="absolute top-0 right-0 bg-primary-100 px-4 py-1 rounded-bl-xl text-xs font-medium text-primary-900">Premium</div>
        <div class="w-12 h-12 bg-primary-100 rounded-full mb-6 flex items-center justify-center">
          <svg width="20" height="22" viewBox="0 0 91 100" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path fill-rule="evenodd" clip-rule="evenodd" d="M38.5213 0H71.8426L50.2602 28.5752H90.6904L19.0338 100L40.8851 51.8383H0.69043L38.5213 0Z" fill="oklch(0.769 0.188 70.08)"/>
          </svg>
        </div>
        <h3 class="text-2xl font-medium mb-1">Immortal</h3>
        <p class="text-sm text-gray-500 mb-6">For world-class leaders.</p>
        <div class="mb-8">
          <span class="text-2xl font-medium">Enterprise</span>
          <div class="text-[10px] text-gray-500 mt-1 font-medium">Contact for pricing</div>
        </div>
        <ul class="space-y-4 mb-8 flex-1">
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Everything in Creator, plus advanced voice and video cloning.
          </li>
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Phone call integration for voice conversations.
          </li>
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Priority support and dedicated success manager.
          </li>
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Exclusive community of transformational leaders.
          </li>
        </ul>
        <button class="w-full bg-[#1A1A1A] text-white py-3 rounded-sm font-medium hover:bg-black transition-colors">Contact Sales</button>
      </div>
    </div>
  </section>

  <!-- FAQ -->
  <section class="py-20 px-6 max-w-3xl mx-auto" id="faq">
    <h2 class="text-3xl font-medium text-center mb-12">Frequently asked questions.</h2>
    <div class="space-y-4">
      {#each faqs as question}
        <div class="border-b border-gray-200 py-4 flex justify-between items-center cursor-pointer group hover:bg-gray-50/50 transition-colors px-2">
          <span class="text-sm md:text-base font-medium text-gray-800">{question}</span>
          <span class="text-gray-400 group-hover:text-black transition-colors">{@html Plus}</span>
        </div>
      {/each}
    </div>
    <div class="mt-12 text-center">
      <button class="border border-gray-300 px-6 py-3 rounded-sm text-xs font-medium hover:bg-gray-50 transition-colors">
        View all Frequently Asked Questions
      </button>
    </div>
  </section>

  <!-- Footer -->
  <footer class="py-16 px-6 border-t border-gray-200 bg-[#F9F8F6]">
    <div class="max-w-7xl mx-auto">
      <div class="flex flex-col md:flex-row justify-between items-start md:items-center gap-8 mb-16">
        <div class="flex items-center gap-2">
           <svg width="24" height="26" viewBox="0 0 91 100" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path fill-rule="evenodd" clip-rule="evenodd" d="M38.5213 0H71.8426L50.2602 28.5752H90.6904L19.0338 100L40.8851 51.8383H0.69043L38.5213 0Z" fill="black"/>
           </svg>
           <span class="font-bold text-lg tracking-wide">Delphi</span>
        </div>
        
        <nav class="flex flex-wrap gap-6 md:gap-8 text-xs font-medium text-gray-600">
          <a href="#features" class="hover:text-black">Features</a>
          <a href="#faq" class="hover:text-black">FAQ</a>
          <a href="#" class="hover:text-black">Blog</a>
          <a href="#" class="hover:text-black">Terms & Conditions</a>
          <a href="#" class="hover:text-black">Privacy Policy</a>
        </nav>

        <div class="flex gap-4 text-gray-800">
          <a href="#" class="hover:text-black">{@html XIcon}</a>
          <a href="#" class="hover:text-black">{@html Instagram}</a>
          <a href="#" class="hover:text-black">{@html LinkedIn}</a>
        </div>
      </div>

      <div class="text-[10px] text-gray-400 leading-relaxed max-w-5xl">
        <p class="mb-2">This AI service is experimental. We are excited to help you, but as with any new service, please use your best judgment before acting on advice. Delphi is a technology platform that enables users to create AI-powered Digital Minds. All content generated by Digital Minds is based on user-provided training data. Delphi does not provide professional advice, medical opinions, legal counsel, or financial guidance. Users maintain complete ownership of their data, which is fully encrypted and never shared or sold.</p>
        <p>Your Digital Mind only speaks your words and does not improvise without consent. We maintain strict privacy standards for all conversations. For more details about how we protect your data and maintain authenticity, see our Terms & Conditions and Privacy Policy.</p>
        <p class="mt-2">By using Delphi, you agree to our terms of service. Message and data rates may apply for SMS and WhatsApp deployments. Message frequency varies based on your configuration.</p>
      </div>
    </div>
  </footer>
</main>

<style>
  :global(body) {
    background-color: #F9F8F6;
    font-family: 'Inter', sans-serif;
  }
  
  .hide-scrollbar::-webkit-scrollbar {
    display: none;
  }
  .hide-scrollbar {
    -ms-overflow-style: none;
    scrollbar-width: none;
  }
</style>

