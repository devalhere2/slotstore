<script>
    import { slide } from "svelte/transition";
    export let types = [];
    let expandedItems = {};
    let rotatedItems = {};

    expandedItems = Object.keys(types).reduce((acc, key) => {
            acc[key] = false;
            return acc;
        }, {});
    rotatedItems = { ...expandedItems };

    function toggleItem(key) {
        if (!expandedItems[key]) {
            expandedItems[key] = true;
            rotatedItems[key] = true;
        } else {
            expandedItems[key] = false;
            setTimeout(() => {
                rotatedItems[key] = false;
                rotatedItems = rotatedItems; 
            }, 250); 
        }
        expandedItems = expandedItems; 
    }
</script>
<!-- svelte-ignore a11y-click-events-have-key-events -->
<!-- svelte-ignore a11y-no-static-element-interactions -->
<main>
    {#each Object.entries(types) as [key, value]}
        <div class="item" on:click={() => toggleItem(key)}>
            <img
                src="/side_bullet.svg"
                alt=""
                class="bullet_icon"
                height="24px"
                class:rotated={rotatedItems[key]}
            /> 
            
            <span class="text">{key}</span>
        </div>
        {#if expandedItems[key]}
            <div
                transition:slide|local={{
                    duration: 250,
                    delay: 100,
                    axis: "y",
                }}
                
            >
                {#each value as type, i}
                    <div class="subitem" on:click={()=>{}}>
                        {#if i == value.length - 1}
                            <img
                                src="/last_line.svg"
                                alt=""
                                class="icon"
                                height="24px"
                            />
                            <span class="subtext">{type}</span>
                        {:else}
                            <img
                                src="/lines.svg"
                                alt=""
                                class="line_icon"
                                height="24px"
                            />
                            <span class="subtext">{type}</span>
                        {/if}
                    </div>
                {/each}
            </div>
        {/if}
    {/each}
</main>



<style lang="scss">
    @import "src/styles.scss";
    main {
        margin: 10px;
        border: 1px solid $primary;
        min-height: 100px;
        border-radius: 5px;
        padding: 5px;;
        background-color: $types_background;
        font-family: "Courier New", Courier, monospace;
        color: $primary;
        user-select: none;
    }
    .item {
        display: flex;
        align-items: center;
        height: 24px;
        cursor: pointer;
        img {
            transition: transform 100ms ease-in-out;
            &.rotated {
                transform: rotate(90deg);
                transition: transform 100ms ease-in-out 0ms;
            }
        }
        &:hover {
            text-decoration: underline;
        }
    }

    .subitem {
        display: flex;
        align-items: center;
        height: 24px;
        cursor: pointer;
        &:hover {
            background-color: $secondary;
        }
    }

    .text {
        line-height: 24px;
        padding-left: 5px;
        font-weight: bold;
    }

    .subtext {
        line-height: 20px;
        padding-left: 5px;
    }
</style>
