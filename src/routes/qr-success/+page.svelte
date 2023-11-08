<script lang="ts">
    /** @type {import('./$types').PageData} */
    export let data;
    
    import {page} from '$app/stores';
    import {get} from 'svelte/store';

    const url = get(page).url.searchParams.get('url');
    const qr_image = `https://api.qrserver.com/v1/create-qr-code/?data=${url}&amp;size=200x200&amp;color=111729`;
    
    function downloadQR() {
        //Initiate a download of png image from a given url
        window.location.href = qr_image;
    }
</script>

<svelte:head>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Outfit&display=swap" rel="stylesheet">
</svelte:head>

<div class="bg-image p-8 md:p-12 2xl:px-64">
    <div class="flex flex-col min-h-screen">
        {#if url != null}
            <header class="mb-[10vh]">
                <img class="max-w-1/2" on:click={() => window.location.href = '/'} alt="Contact Logo" src="/asset/logo-qr-generator.svg" />
            </header>

            <div class = "flex flex-col px-4">
                <div class="p-6 bg-white mb-[10vh] mx-auto rounded-xl">
                    <img src={qr_image} alt="QR Image">
                </div>

                <div class = "flex flex-row justify-center gap-8">
                    <button on:click={downloadQR} class="px-6 py-4 items-center justify-center bg-[#3662E3] text-[#F2F5F9] font-outfit rounded-xl flex flex-row gap-4 md:max-w-[30vw] lg:max-w-[15vw] 2xl:max-w-[10vw]">
                        <p>Download</p>
                        <svg xmlns="http://www.w3.org/2000/svg" height="1em" viewBox="0 0 512 512"><style>svg{fill:#adbdeb}</style><path d="M256 464a208 208 0 1 1 0-416 208 208 0 1 1 0 416zM256 0a256 256 0 1 0 0 512A256 256 0 1 0 256 0zM376.9 294.6c4.5-4.2 7.1-10.1 7.1-16.3c0-12.3-10-22.3-22.3-22.3H304V160c0-17.7-14.3-32-32-32l-32 0c-17.7 0-32 14.3-32 32v96H150.3C138 256 128 266 128 278.3c0 6.2 2.6 12.1 7.1 16.3l107.1 99.9c3.8 3.5 8.7 5.5 13.8 5.5s10.1-2 13.8-5.5l107.1-99.9z"/></svg>
                    </button>
                    <button class=" px-6 py-4 items-center justify-center bg-[#3662E3] text-[#F2F5F9] font-outfit rounded-xl flex flex-row gap-4 md:max-w-[30vw] lg:max-w-[15vw] 2xl:max-w-[10vw]">
                        <p>Share</p>
                        <svg xmlns="http://www.w3.org/2000/svg" height="1em" viewBox="0 0 576 512"><path d="M400 255.4V240 208c0-8.8-7.2-16-16-16H352 336 289.5c-50.9 0-93.9 33.5-108.3 79.6c-3.3-9.4-5.2-19.8-5.2-31.6c0-61.9 50.1-112 112-112h48 16 32c8.8 0 16-7.2 16-16V80 64.6L506 160 400 255.4zM336 240h16v48c0 17.7 14.3 32 32 32h3.7c7.9 0 15.5-2.9 21.4-8.2l139-125.1c7.6-6.8 11.9-16.5 11.9-26.7s-4.3-19.9-11.9-26.7L409.9 8.9C403.5 3.2 395.3 0 386.7 0C367.5 0 352 15.5 352 34.7V80H336 304 288c-88.4 0-160 71.6-160 160c0 60.4 34.6 99.1 63.9 120.9c5.9 4.4 11.5 8.1 16.7 11.2c4.4 2.7 8.5 4.9 11.9 6.6c3.4 1.7 6.2 3 8.2 3.9c2.2 1 4.6 1.4 7.1 1.4h2.5c9.8 0 17.8-8 17.8-17.8c0-7.8-5.3-14.7-11.6-19.5l0 0c-.4-.3-.7-.5-1.1-.8c-1.7-1.1-3.4-2.5-5-4.1c-.8-.8-1.7-1.6-2.5-2.6s-1.6-1.9-2.4-2.9c-1.8-2.5-3.5-5.3-5-8.5c-2.6-6-4.3-13.3-4.3-22.4c0-36.1 29.3-65.5 65.5-65.5H304h32zM72 32C32.2 32 0 64.2 0 104V440c0 39.8 32.2 72 72 72H408c39.8 0 72-32.2 72-72V376c0-13.3-10.7-24-24-24s-24 10.7-24 24v64c0 13.3-10.7 24-24 24H72c-13.3 0-24-10.7-24-24V104c0-13.3 10.7-24 24-24h64c13.3 0 24-10.7 24-24s-10.7-24-24-24H72z"/></svg>
                    </button>
                </div>
            </div>

        {:else}
            No Parameter is set
        {/if}
    </div>

</div>
