<script>
    import { onMount } from 'svelte';
    import { page } from '$app/stores';
    import programs from '../../data/eoi.json';

    let program;
    let id;

    // Get the id from the URL
    $: id = $page.params.id;

    // Find the program with the matching id
    $: program = programs.find(p => p.id === id);
</script>

{#if program}
    <div class="container mx-auto p-4">
        <h1 class="text-2xl font-bold">{program.title}</h1>
        <img src="/img/{program.image1}" alt="{program.title}" class="w-full object-contain h-64 mx-auto my-4">
        <p class="text-justify">{program.desc}</p>
        <a href="{program.apply}" class="text-blue-500 underline">Apply Now</a>
    </div>
{:else}
    <p>Loading...</p>
{/if}
