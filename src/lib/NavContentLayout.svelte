<script lang="ts">
    import { page } from "$app/stores";
    import { Dropdown } from "flowbite-svelte";
</script>

<div class="absolute flex justify-between top-0 left-0 right-0 p-1 px-3 rounded-b-xl bg-[#e69900] text-white h-fit z-50" style="view-transition-name: navbar">
    <a style="view-transition-name: {$page.url.pathname.slice(1)};" href="/">Zurück</a>
    {#if $$slots.settings}    
        <button>
            <svg class="w-5 h-5 text-white" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="currentColor" viewBox="0 0 20 20">
                <path d="M18 7.5h-.423l-.452-1.09.3-.3a1.5 1.5 0 0 0 0-2.121L16.01 2.575a1.5 1.5 0 0 0-2.121 0l-.3.3-1.089-.452V2A1.5 1.5 0 0 0 11 .5H9A1.5 1.5 0 0 0 7.5 2v.423l-1.09.452-.3-.3a1.5 1.5 0 0 0-2.121 0L2.576 3.99a1.5 1.5 0 0 0 0 2.121l.3.3L2.423 7.5H2A1.5 1.5 0 0 0 .5 9v2A1.5 1.5 0 0 0 2 12.5h.423l.452 1.09-.3.3a1.5 1.5 0 0 0 0 2.121l1.415 1.413a1.5 1.5 0 0 0 2.121 0l.3-.3 1.09.452V18A1.5 1.5 0 0 0 9 19.5h2a1.5 1.5 0 0 0 1.5-1.5v-.423l1.09-.452.3.3a1.5 1.5 0 0 0 2.121 0l1.415-1.414a1.5 1.5 0 0 0 0-2.121l-.3-.3.452-1.09H18a1.5 1.5 0 0 0 1.5-1.5V9A1.5 1.5 0 0 0 18 7.5Zm-8 6a3.5 3.5 0 1 1 0-7 3.5 3.5 0 0 1 0 7Z"/>
            </svg>
        </button>
        <Dropdown class="shadow-2xl">
            <slot name="settings" />
        </Dropdown>
    {/if}
</div>
<main class="flex flex-col justify-start items-center gap-1 mt-7 p-2 m-auto" style="width: calc(100vmin - 1.75rem); height: calc(100vmin - 1.75rem);">
    <slot />
</main>