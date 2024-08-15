<script>
    import { onMount } from 'svelte';

    let types = [];

    onMount(async () => {
        const response = await fetch('/Types.json');
        types = await response.json();
    });
</script>

<main>
    {#each Object.entries(types) as [key, value]}
        <div id="key">
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                <circle cx="12" cy="12" r="10" stroke="black" stroke-width="2"/>
                <line x1="12" y1="6" x2="12" y2="12" stroke="black" stroke-width="2"/>
                <line x1="12" y1="12" x2="16" y2="16" stroke="black" stroke-width="2"/>
            </svg>
            {key}
        </div>
    {/each}
</main>

<style>
    main {
        margin: 10px;
        background-color: cyan;
        font-family: 'Courier New', Courier, monospace;
        font-weight: bold;
    }
</style>