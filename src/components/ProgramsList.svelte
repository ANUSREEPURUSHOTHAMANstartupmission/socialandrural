<script>
    import programs from '../data/eoi.json';

    function navigateToDetailPage(id) {
        window.location.href = `/${id}`;
    }

</script>

<div class="px-6 md:px-8">
    <div class="md:grid-cols-3 lg:grid-cols-4 sm:grid-cols-2 grid-cols-1 grid gap-4 px-4">
        {#each programs as program}
            <div class="pb-8 relative flex flex-col cursor-pointer border shadow-2xl bg-white" on:click={() => navigateToDetailPage(program.id)}>
                <div class="card cursor-pointer m-4" style="background-image: url('/img/{program.image1}');"></div>
                <div class="pt-2">
                    <div class="text-black w-full p-4 text-lg flex uppercase" style="font-family: Jost, sans-serif;">{program.title}</div>
                </div>
            </div>
        {/each}
    </div>
</div>

<style>
    .card {
        background-color: white;
        height: 14rem;
        background-position: center;
        background-repeat: no-repeat;
        background-size: cover;
    }

    .card-title:hover {
        cursor: default;
        color: rgb(249 66 30 / var(--tw-text-opacity));
    }
</style>
