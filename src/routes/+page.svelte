<main>
    <div id="types">1</div>
    <div id="body">2</div>
    <div id="saved">3</div>
</main>

<style lang="scss">
    @import '../styles.scss';
    main {
        display: flex;
        height: calc(100vh - 60px);
        #types {
            width: 15%;
            background-color: $types_background;
        }
        #body {
            flex: 1;
        }   
        #saved {
            width: 25%;
        }
    }
</style>