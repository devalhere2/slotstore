<main>
    <div id="types">
        <Types></Types>
    </div>
    <div id="body">
        <Body></Body>
    </div>
    <div id="other">
        <Other></Other>
    </div>
</main>

<script>
    import  Body  from '$lib/comp/Body.svelte';
    import  Other  from '$lib/comp/Other.svelte';
    import  Types  from '$lib/comp/Types.svelte';

</script>

<style lang="scss">
    @import 'src/styles.scss';
    main {
        box-sizing: border-box;
        display: flex;
        min-height: calc(100vh - 60px);
        #types {
            min-width: 200px;
            border-right: 1px solid rgba($primary, 0.1);
        }
        #body {
            flex: 1;
            background-color: aliceblue;
        }   
        #other {
            width: 30px;
            background-color: rgba(255, 182, 193, 0.5);
        }
    }
</style>