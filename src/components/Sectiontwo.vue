<template>
  <section class="sticky top-0 h-screen z-20 bg-[#1E2A78]">
        <div class="grid grid-cols-1 md:grid-cols-2 min-h-screen md:h-full">
      
      <!-- Colonna sinistra: testo -->
      <div class="flex flex-col justify-center px-6 md:px-12 py-10 space-y-6">
        <h2 class="text-3xl md:text-4xl font-bold text-[#FADACF]">Branding</h2>
        <p class="text-base leading-relaxed text-white">
         Il progetto nasce dall’esigenza di valorizzare un brand poco riconoscibile all’interno del 
            contesto della grande distribuzione. Nel mio caso, ho selezionato Cholula, una salsa 
            piccante con un’identità visiva poco definita, per svilupparne una nuova direzione 
            creativa.
        </p>
        <div>
          <h3 class="text-lg font-semibold text-[#FADACF] mb-2">TOOL</h3>
          <div class="flex flex-wrap gap-4">
            <img src="./9.png" alt="Figma" class="w-8 h-8" />
            <img src="./9.png" alt="Photoshop" class="w-8 h-8" />
            <img src="./5.png" alt="Webflow" class="w-8 h-8" />
          </div>
        </div>
      </div>

      <!-- Colonna destra: mockup -->
      <div class="flex items-center justify-center px-6 py-8 md:py-0">
        <div class="w-[300px] h-[400px] md:w-[500px] md:h-[400px] overflow-hidden rounded-xl shadow-2xl">
          <img src="/ribs.png" alt="ribs" class="w-full h-full object-cover" />
        </div>
      </div>

    </div>

  </section>
</template>
