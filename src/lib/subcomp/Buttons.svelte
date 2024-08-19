<script>
    import Switch from "./Switch.svelte";
    import Dropdown from "./Dropdown.svelte";
    import { slide } from "svelte/transition";
    import { sineInOut } from "svelte/easing";

    let default_switch = "New";
    let default_drop = "All";
    let default_top = '';

    function switchValue(event) {
        default_switch = event.detail.text;
        if (default_switch === "New") {
            default_top = '';
        } else {
            default_top = "Weekly";
        }
    }
    function topValue(event) {
        default_top = event.detail.text;
    }
    function dropValue(event) {
        default_drop = event.detail.text;
    }
</script>

<div id="button_bar" > 
    <Switch color="#001524" li={["New", "Top"]} on:switchvalue={switchValue} />
    {#if default_switch === "Top"}
    <div transition:slide={{
        duration: 500,
        easing: sineInOut,
        axis: "x",
    }}>
        <Switch color="#001524" li={["Weekly","Monthly", "All_Time"]} on:switchvalue={topValue} />
    </div>
    {/if}
    <Dropdown
        color="#001524"
        li={["HTML", "Svelte", "Vue", "React", "Angular"]}
        on:dropvalue={dropValue}
    />
</div>

<style lang="scss">
    #button_bar {
        display: flex;
        align-items: center;
        justify-content: start;
    }
</style>