<script>
    import { createEventDispatcher } from "svelte";
    const dispatch = createEventDispatcher();

    export let li = ["one", "two", "three"];
    export let color = "#000000";
    let i = 0;

    let colorRGB = "0, 0, 0";
    function hexToRgb(hex) {
        let bigint = parseInt(hex.slice(1), 16);
        let r = (bigint >> 16) & 255;
        let g = (bigint >> 8) & 255;
        let b = bigint & 255;
        return `${r}, ${g}, ${b}`;
    }
    $: colorRGB = color.startsWith("#") ? hexToRgb(color) : "0, 0, 0";

    function increment() {
        i = (i + 1) % li.length;
        dispatch("switchvalue", {
            text: li[i],
        });
    }
</script>

<main style="--color-var: {color}; --color-rgb: {colorRGB};">
    <button on:click={increment}>
        {li[i]}
    </button>
</main>

<style lang="scss">
    button {
        height: 30px;
        font-weight: bold;
        cursor: pointer;
        font-size: 16px;
        padding: 10px;
        display: flex;
        align-items: center;
        justify-content: center;
        margin-left: 10px;
        border: 1px solid var(--color-var);
        border-radius: 50px;
        background-color: rgba(var(--color-rgb), 0.1);
        color: var(--color-var);
    }
</style>
