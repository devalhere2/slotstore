<script>
    import { onMount } from "svelte";
    import Tree from "../subcomp/Tree.svelte";
    let types = [];
    onMount(async () => {
        const response = await fetch("/Types.json");
        types = await response.json();
    });
    
</script>

<Tree types = {types}></Tree>

