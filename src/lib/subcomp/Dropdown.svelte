<script>
    import { createEventDispatcher } from "svelte";
    const dispatch = createEventDispatcher();
    

    let isVisible = false;
    let li = ["All","HTML", "Svelte", "React", "Vue", "Angular", "Other..."];

    function toggleVisibility() {
        isVisible = !isVisible;
    }
    function replace(val) {
        let temp = li[0];
        let index = li.indexOf(val);
        if (index !== -1) {
            li[index] = temp;
            li[0] = val;
        }
        dispatch("dropvalue", {
            text: val,
        });
        isVisible = false;
    }
</script>

<main>
    <div class="dropdown">
        <button on:click={toggleVisibility} id="top_button">
            {li[0]}
            <img
                src={isVisible ? "up_arrow.svg" : "down_arrow.svg"}
                width="10px"
                style="margin-left: 2px;"
                alt=""
            />
        </button>
        <div class="options" class:visible={isVisible}>
            {#each li as type, i}
                {#if i !== 0}
                    <button
                        on:click={() => {
                            replace(type);
                        }}>{type}</button
                    >
                {/if}
            {/each}
        </div>
    </div>
</main>

<style lang="scss">
    @import "src/styles.scss";

    .dropdown {
        position: relative;
        display: inline-block;
    }

    #top_button {
        font-family: "Courier New", Courier, monospace;
        height: 30px;
        font-weight: bold;
        width: 100px;
        cursor: pointer;
        font-size: 16px;
        display: flex;
        align-items: center;
        justify-content: center;
        margin-left: 10px;
        z-index: 1;
        border: 1px solid $primary;
        border-top-left-radius: 14px;
        border-top-right-radius: 14px;
        background-color: rgba($primary, 0.1);
        color: $primary;
    }

    .options {
        position: absolute;
        margin-left: 10px;
        top: 100%;
        left: 0;
        display: none;
        flex-direction: column;
        background-color: #f9f9f9;
        background-color: rgba($secondary, 0.1);
        box-shadow: 0px 8px 16px 0px rgba($primary, 0.2);
        z-index: 1;
        border-bottom-left-radius: 14px;
        border-bottom-right-radius: 14px;
        overflow: hidden;
    }

    .options.visible {
        display: flex;
    }

    .options button {
        text-decoration: none;
        font-family: "Courier New", Courier, monospace;
        display: block;
        border: none;
        width: 100px;
        height: 30px;
        font-size: 14px;
        text-align: left;
        background-color: white;
        cursor: pointer;
        padding: 0 10px; // Add some padding for better text alignment
    }

    .options button:hover {
        background-color: $secondary;
    }

    // Style for the last button to respect bottom border radius
    .options button:last-child {
        border-bottom-left-radius: 14px;
        border-bottom-right-radius: 14px;
    }
</style>
