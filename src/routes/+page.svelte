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
    "https://images.unsplash.com/photo-1515694346937-94d85e41e6f0?q=80&w=600&auto=format&fit=crop", // Woman in field
    "https://images.unsplash.com/photo-1464226184884-fa280b87c399?q=80&w=600&auto=format&fit=crop", // Garden/farm
    "https://images.unsplash.com/photo-1556910103-1c02745aae4d?q=80&w=600&auto=format&fit=crop", // Family cooking
    "https://images.unsplash.com/photo-1488459716781-31db52582fe9?q=80&w=600&auto=format&fit=crop", // Farmers market
    "https://images.unsplash.com/photo-1490818387583-1baba5e638af?q=80&w=600&auto=format&fit=crop", // Picnic/outdoor
    "https://images.unsplash.com/photo-1512621776951-a57141f2eefd?q=80&w=600&auto=format&fit=crop"  // Healthy food
  ];

  const benefitCards = [
    {
      title: "Instant ingredient insights.",
      desc: "Scan any barcode and get immediate safety alerts about hidden toxins, allergens, and questionable ingredients.",
      image: "https://images.unsplash.com/photo-1534452203293-494d7ddbf7e0?q=80&w=800&auto=format&fit=crop"
    },
    {
      title: "Customizable safety filters.",
      desc: "Set your family's preferences and dietary needs. Olive alerts you to ingredients that don't meet your standards.",
      image: "https://images.unsplash.com/photo-1583258292688-d0213dc5a3a8?q=80&w=800&auto=format&fit=crop"
    },
    {
      title: "Comprehensive ingredient database.",
      desc: "Access our proprietary database of thousands of ingredients with clear explanations of what they are and why they matter.",
      image: "https://images.unsplash.com/photo-1542838132-92c53300491e?q=80&w=800&auto=format&fit=crop"
    }
  ];

  const steps = [
    {
      step: 1,
      title: "Download Olive.",
      desc: "Get the free app from the App Store or Google Play. Create your profile and set your family's dietary preferences and safety filters.",
      image: "plan"
    },
    {
      step: 2,
      title: "Scan any product.",
      desc: "Point your camera at any barcode while shopping. Olive instantly analyzes the ingredients against your preferences.",
      image: "schedule"
    },
    {
      step: 3,
      title: "Get instant alerts.",
      desc: "See color-coded safety ratings and detailed breakdowns of concerning ingredients. Know exactly what you're buying.",
      image: "results"
    },
    {
      step: 4,
      title: "Make informed choices.",
      desc: "Browse safer alternatives and build your personal list of trusted products. Shop with confidence every time.",
      image: "notes"
    }
  ];

  const faqs = [
    "How does Olive identify harmful ingredients?",
    "Can I customize what ingredients to avoid?",
    "Does Olive work with all products?",
    "Is my shopping data kept private?",
    "How is Olive different from other scanning apps?"
  ];
</script>

<Header />

<main class="w-full overflow-x-hidden">
  <!-- Hero Section -->
  <section class="pt-32 pb-16 md:pt-40 md:pb-24 px-6 text-center max-w-7xl mx-auto">
    <h1 class="text-4xl md:text-6xl lg:text-7xl font-medium tracking-tight text-[#1A1A1A] mb-6 leading-[1.1]">
      Safe groceries.<br />Happy families.
    </h1>
    <p class="text-gray-600 text-lg md:text-xl max-w-3xl mx-auto mb-10 leading-relaxed font-light">
      Scan any barcode and instantly know if a product is safe for your family. No more confusing labels or hidden toxins.
    </p>
    <button class="bg-[#1A1A1A] text-white px-8 py-3.5 rounded-sm font-medium hover:bg-black transition-colors">
      Download Free App
    </button>
  </section>

  <!-- Hero Images Scroll -->
  <div class="w-full overflow-x-auto pb-12 hide-scrollbar">
    <div class="flex gap-4 px-6 min-w-max">
      {#each heroImages as img, i}
        <div class="relative w-48 h-64 md:w-64 md:h-80 rounded-3xl overflow-hidden flex-shrink-0">
          <img src={img} alt="Lifestyle" class="w-full h-full object-cover" />
        </div>
      {/each}
    </div>
  </div>

  <!-- App Feature Section -->
  <section class="py-20 px-6 max-w-7xl mx-auto">
    <div class="bg-white rounded-[40px] p-8 md:p-16 flex flex-col md:flex-row items-center gap-12 shadow-sm">
      <!-- Phone Mockup -->
      <div class="w-full md:w-1/2 flex justify-center">
        <div class="relative w-[280px] h-[580px] bg-black rounded-[40px] border-[8px] border-black shadow-2xl overflow-hidden">
          <div class="absolute top-0 left-0 right-0 h-6 bg-black z-20 flex justify-center">
            <div class="w-20 h-4 bg-black rounded-b-xl"></div>
          </div>
          <div class="w-full h-full bg-white pt-10 px-4 overflow-hidden flex flex-col">
            <!-- Mock Scanning UI -->
            <div class="flex justify-between items-center mb-6">
              <div class="text-xs font-bold">Olive</div>
              <div class="w-8 h-8 rounded-full bg-gray-100 flex items-center justify-center">
                <div class="w-4 h-4 rounded-full bg-primary-500"></div>
              </div>
            </div>
            <div class="mb-6 text-center">
              <div class="text-xs text-gray-500 mb-2">Scan Result</div>
              <div class="text-xl font-bold">Organic Granola</div>
            </div>
            <div class="space-y-3">
              <div class="h-20 bg-primary-50 rounded-xl w-full border border-primary-200 p-3">
                <div class="flex items-center justify-between mb-2">
                  <div class="text-xs font-medium">Safety Score</div>
                  <div class="text-xs font-bold text-primary-700">A+</div>
                </div>
                <div class="w-full h-2 bg-primary-400 rounded"></div>
              </div>
              <div class="h-20 bg-orange-50 rounded-xl w-full border border-orange-200 p-3">
                <div class="flex items-center justify-between mb-2">
                  <div class="text-xs font-medium">Contains Allergen</div>
                  <div class="text-xs font-bold text-orange-700">!</div>
                </div>
                <div class="w-3/4 h-2 bg-orange-400 rounded"></div>
              </div>
              <div class="h-20 bg-gray-50 rounded-xl w-full border border-gray-100 p-3">
                <div class="text-xs font-medium mb-2">12 Ingredients</div>
                <div class="w-full h-1 bg-gray-300 rounded"></div>
              </div>
            </div>
          </div>
        </div>
      </div>
      
      <!-- Content -->
      <div class="w-full md:w-1/2 space-y-8">
        <h2 class="text-3xl md:text-4xl font-medium leading-tight text-[#1A1A1A]">
          Ingredient safety at your fingertips.<br />
          Scan any barcode to see instant safety ratings, detailed ingredient breakdowns, and personalized alerts based on your family's needs. Shopping for safe products has never been easier.
        </h2>
        <div class="flex items-center justify-between pt-4">
          <button class="flex items-center gap-2 text-[#1A1A1A] font-medium hover:opacity-70 transition-opacity">
            {@html PlayCircle}
            Watch demo
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
        Your family deserves the cleanest, safest products.
      </h2>
      <p class="text-gray-600 text-lg font-light leading-relaxed">
        Every parent wants to protect their children, but ingredient labels are confusing and overwhelming. Olive gives you the power to make informed choices in seconds, so you can shop with confidence and peace of mind. Because the health of your family shouldn't be a guessing game.
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
      "Olive has completely changed how I shop for my family. I used to spend hours researching ingredients and still felt uncertain. Now I just scan and know instantly if something is safe. It's given me such peace of mind."
    </blockquote>
    <div class="flex flex-col items-center gap-3">
      <img src="https://images.unsplash.com/photo-1438761681033-6461ffad8d80?q=80&w=100&auto=format&fit=crop" alt="Parent testimonial" class="w-12 h-12 rounded-full object-cover" />
      <div class="text-center">
        <div class="font-medium text-sm">Sarah Mitchell</div>
        <div class="text-gray-500 text-xs">Mother of Two</div>
      </div>
    </div>
  </section>

  <!-- Stats Grid -->
  <section class="py-12 px-6 max-w-7xl mx-auto border-t border-gray-200" id="features">
    <div class="grid md:grid-cols-3 gap-8 text-center md:text-left">
      <div>
        <h3 class="text-xl font-medium mb-2">Scan in 2 seconds.</h3>
        <p class="text-gray-500 text-sm font-light">Point your camera at any barcode and get instant results. No typing, no waiting.</p>
      </div>
      <div>
        <h3 class="text-xl font-medium mb-2">50,000+ ingredients tracked.</h3>
        <p class="text-gray-500 text-sm font-light">Our proprietary database covers thousands of products with detailed safety information.</p>
      </div>
      <div>
        <h3 class="text-xl font-medium mb-2">Personalized for your family.</h3>
        <p class="text-gray-500 text-sm font-light">Set custom filters for allergies, sensitivities, and dietary preferences.</p>
      </div>
    </div>
  </section>

  <!-- How it works -->
  <section class="py-20 px-6 max-w-7xl mx-auto" id="how-it-works">
    <div class="mb-16 max-w-md">
      <h2 class="text-4xl font-medium mb-6">How it works.</h2>
      <p class="text-gray-600 font-light">Olive makes ingredient checking effortless. Download the app, scan any product, and get instant safety alerts tailored to your family's needs. It's that simple.</p>
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
      <!-- Database Card -->
      <div class="bg-[#111] rounded-[40px] p-8 md:p-12 text-white min-h-[500px] flex flex-col relative overflow-hidden">
        <div class="relative z-10">
          <h3 class="text-sm font-medium text-gray-400 mb-2">Comprehensive and growing.</h3>
          <h2 class="text-2xl md:text-3xl font-medium max-w-xs">Our proprietary ingredient database is constantly updated.</h2>
        </div>
        <!-- Abstract ingredient visual -->
        <div class="absolute inset-0 flex items-center justify-center opacity-20 mt-20">
           <svg viewBox="0 0 200 100" class="w-full h-full text-primary-500 fill-current">
              <!-- Simplified ingredient representation -->
              {#each Array(100) as _, i}
                <circle cx={Math.random() * 200} cy={Math.random() * 100} r={Math.random() * 1.5} />
              {/each}
           </svg>
        </div>
      </div>

      <!-- Privacy Card -->
      <div class="bg-[#111] rounded-[40px] p-8 md:p-12 text-white min-h-[500px] flex flex-col relative overflow-hidden">
        <div class="relative z-10">
          <h3 class="text-sm font-medium text-gray-400 mb-2">Your shopping stays private.</h3>
          <h2 class="text-2xl md:text-3xl font-medium max-w-xs">We never sell your data or share your shopping history.</h2>
        </div>
        <!-- Blurred Text Visual -->
        <div class="absolute inset-0 flex items-center justify-center mt-20 overflow-hidden">
           <div class="text-4xl font-mono text-gray-600 opacity-20 blur-sm select-none break-all p-8">
             Parab|%b$9yT Glute|I7n/e Artif|&5a! BHA|?Pm_Lw
           </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Pricing Section -->
  <section class="py-24 px-6 max-w-7xl mx-auto" id="download">
    <div class="text-center mb-16">
      <h2 class="text-3xl md:text-4xl font-medium mb-4">Safe shopping for everyone.</h2>
      <p class="text-gray-500 font-light max-w-2xl mx-auto">Start with our free plan and upgrade when you need advanced features. Because every family deserves access to ingredient safety information.</p>
    </div>

    <div class="grid md:grid-cols-2 gap-6 max-w-4xl mx-auto">
      <!-- Free Plan -->
      <div class="bg-white rounded-[32px] p-8 flex flex-col">
        <div class="w-12 h-12 bg-primary-100 rounded-full mb-6 flex items-center justify-center">
          <svg class="w-6 h-6 text-primary-600" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path opacity="0.5" d="M16.6765 3.05148C18.9425 3.05148 20.7794 4.88843 20.7794 7.15442C20.7794 9.42043 18.9425 11.2574 16.6765 11.2574H12.5735V7.15442C12.5735 4.88843 14.4105 3.05148 16.6765 3.05148Z" fill="currentColor"/>
            <path d="M3 7.15442C3 4.88843 4.83695 3.05148 7.10294 3.05148C9.36895 3.05148 11.2059 4.88843 11.2059 7.15442V11.2574H7.10294C4.83695 11.2574 3 9.42043 3 7.15442Z" fill="currentColor"/>
            <path d="M7.10294 20.8309C4.83695 20.8309 3 18.9939 3 16.7279C3 14.4619 4.83695 12.625 7.10294 12.625H11.2059V16.7279C11.2059 18.9939 9.36895 20.8309 7.10294 20.8309Z" fill="currentColor"/>
            <path d="M20.7794 16.7279C20.7794 18.9939 18.9425 20.8309 16.6765 20.8309C14.4105 20.8309 12.5735 18.9939 12.5735 16.7279V12.625H16.6765C18.9425 12.625 20.7794 14.4619 20.7794 16.7279Z" fill="currentColor"/>
          </svg>
        </div>
        <h3 class="text-2xl font-medium mb-1">Free</h3>
        <p class="text-sm text-gray-500 mb-6">Start your safe shopping journey.</p>
        <div class="mb-8">
          <span class="text-2xl font-medium">$0</span>
          <span class="text-gray-400 text-sm">/forever</span>
        </div>
        <ul class="space-y-4 mb-8 flex-1">
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Unlimited barcode scans
          </li>
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Basic ingredient safety ratings
          </li>
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Common allergen alerts
          </li>
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Save favorite products
          </li>
        </ul>
        <button class="w-full bg-[#1A1A1A] text-white py-3 rounded-sm font-medium hover:bg-black transition-colors">Download Free</button>
      </div>

      <!-- Premium Plan -->
      <div class="bg-white rounded-[32px] p-8 flex flex-col relative overflow-hidden">
        <div class="absolute top-0 right-0 bg-primary-100 px-4 py-1 rounded-bl-xl text-xs font-medium text-primary-800">Most Popular</div>
        <div class="w-12 h-12 bg-primary-200 rounded-full mb-6 flex items-center justify-center">
          <svg class="w-6 h-6 text-primary-700" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path opacity="0.5" d="M16.6765 3.05148C18.9425 3.05148 20.7794 4.88843 20.7794 7.15442C20.7794 9.42043 18.9425 11.2574 16.6765 11.2574H12.5735V7.15442C12.5735 4.88843 14.4105 3.05148 16.6765 3.05148Z" fill="currentColor"/>
            <path d="M3 7.15442C3 4.88843 4.83695 3.05148 7.10294 3.05148C9.36895 3.05148 11.2059 4.88843 11.2059 7.15442V11.2574H7.10294C4.83695 11.2574 3 9.42043 3 7.15442Z" fill="currentColor"/>
            <path d="M7.10294 20.8309C4.83695 20.8309 3 18.9939 3 16.7279C3 14.4619 4.83695 12.625 7.10294 12.625H11.2059V16.7279C11.2059 18.9939 9.36895 20.8309 7.10294 20.8309Z" fill="currentColor"/>
            <path d="M20.7794 16.7279C20.7794 18.9939 18.9425 20.8309 16.6765 20.8309C14.4105 20.8309 12.5735 18.9939 12.5735 16.7279V12.625H16.6765C18.9425 12.625 20.7794 14.4619 20.7794 16.7279Z" fill="currentColor"/>
          </svg>
        </div>
        <h3 class="text-2xl font-medium mb-1">Premium</h3>
        <p class="text-sm text-gray-500 mb-6">Complete family protection.</p>
        <div class="mb-8">
          <span class="text-2xl font-medium">$4.99</span>
          <span class="text-gray-400 text-sm">/month</span>
        </div>
        <ul class="space-y-4 mb-8 flex-1">
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Everything in Free, plus:
          </li>
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Advanced customizable filters for your family's specific needs
          </li>
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Detailed ingredient explanations and health impact reports
          </li>
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Safer product recommendations and alternatives
          </li>
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Family sharing for up to 5 profiles
          </li>
        </ul>
        <button class="w-full bg-[#1A1A1A] text-white py-3 rounded-sm font-medium hover:bg-black transition-colors">Start Free Trial</button>
      </div>
    </div>
  </section>

  <!-- FAQ -->
  <section class="py-20 px-6 max-w-3xl mx-auto" id="faq">
    <h2 class="text-3xl font-medium text-center mb-12">Your questions answered.</h2>
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
          <svg class="w-6 h-6 text-primary-600" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path opacity="0.5" d="M16.6765 3.05148C18.9425 3.05148 20.7794 4.88843 20.7794 7.15442C20.7794 9.42043 18.9425 11.2574 16.6765 11.2574H12.5735V7.15442C12.5735 4.88843 14.4105 3.05148 16.6765 3.05148Z" fill="currentColor"/>
            <path d="M3 7.15442C3 4.88843 4.83695 3.05148 7.10294 3.05148C9.36895 3.05148 11.2059 4.88843 11.2059 7.15442V11.2574H7.10294C4.83695 11.2574 3 9.42043 3 7.15442Z" fill="currentColor"/>
            <path d="M7.10294 20.8309C4.83695 20.8309 3 18.9939 3 16.7279C3 14.4619 4.83695 12.625 7.10294 12.625H11.2059V16.7279C11.2059 18.9939 9.36895 20.8309 7.10294 20.8309Z" fill="currentColor"/>
            <path d="M20.7794 16.7279C20.7794 18.9939 18.9425 20.8309 16.6765 20.8309C14.4105 20.8309 12.5735 18.9939 12.5735 16.7279V12.625H16.6765C18.9425 12.625 20.7794 14.4619 20.7794 16.7279Z" fill="currentColor"/>
          </svg>
          <span class="font-bold text-lg tracking-wide">Olive</span>
        </div>
        
        <nav class="flex flex-wrap gap-6 md:gap-8 text-xs font-medium text-gray-600">
          <a href="#features" class="hover:text-black">Features</a>
          <a href="#how-it-works" class="hover:text-black">How it Works</a>
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
        <p class="mb-2">Olive is a technology company providing ingredient information and safety ratings. The information provided by Olive is for educational and informational purposes only and should not be considered medical advice. Olive does not diagnose, treat, or prevent any health conditions. Always consult with a qualified healthcare provider regarding any health concerns or before making dietary changes.</p>
        <p class="mb-2">Ingredient safety ratings are based on publicly available research and data. Individual reactions to ingredients may vary. Olive is not responsible for any adverse reactions or health outcomes resulting from product choices.</p>
        <p class="mt-2">By using Olive, you agree to our Terms of Service and Privacy Policy. We never sell your personal data or shopping information to third parties.</p>
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

