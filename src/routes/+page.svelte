<svelte:head>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Outfit&display=swap" rel="stylesheet">
</svelte:head>

<div class="bg-image px-2">
  <div class="flex flex-col min-h-screen pt-[30vh] mx-auto">
    <img alt="Contact Logo" class="mx-auto mb-6 lg:mb-12 md:w-1/4" src="/asset/logo-qr-generator.svg" />

    <!-- Search Bar -->
    <div class="px-4 flex flex-col md:px-[15vw] lg:px-[25vw]">
      <input type="search" class="min-w-[100%] p-4 pl-6 lg:p-5 lg:pl-8 text-sm border-[#3662E3] border-2 rounded-xl bg-black/25 text-[#F2F5F9] placeholder:text-[#364153] font-outfit" name="qr" placeholder="Enter an URL" required>

      <button class="absolute right-0 transform -translate-y-[-25%] -translate-x-8 md:-translate-x-[17vw] lg:-translate-x-[26vw] lg:translate-y-[23%] px-8 py-2 lg:px-10 lg:py-3 text-sm bg-[#3662E3] text-[#F2F5F9] font-outfit rounded-xl">QR Code</button>
    </div>
  </div>
</div>
  
<style>
  .bg-image {
    background-image: url('/asset/bg-illustration.svg');
    background-color: #111729;
    background-size: cover;
    background-position: center;
  }
</style>
