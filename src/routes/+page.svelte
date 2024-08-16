<main>
    <div id="types">
        <Types></Types>
    </div>
    <div id="body">
        <Body></Body>
    </div>
    <div id="own">
        <Own></Own>
    </div>
</main>

<script>
    import  Body  from '$lib/comp/Body.svelte';
    import  Own  from '$lib/comp/Own.svelte';
    import  Types  from '$lib/comp/Types.svelte';

</script>

<style lang="scss">
    @import 'src/styles.scss';
    main {
        display: flex;
        min-height: calc(100vh - 60px);
        #types {
            min-width: 15%;
            background-color: $types_background;
        }
        #body {
            flex: 1;
            background-color: aliceblue;
        }   
        #own {
            width: 25%;
            background-color: rgba(255, 182, 193, 0.5);
        }
    }
</style>