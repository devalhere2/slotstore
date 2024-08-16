<script>
    export let li = ['one', 'two', 'three'];
    let i = 0;
    function increment() {
        i = (i + 1) % li.length;
    }
</script>

<main>
    <button on:click={increment}>
        {li[i]}
    </button>
</main>
