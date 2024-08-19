<script>
    let current_display = "Nav";
</script>

<main style={current_display ? 'height:50px': ''}>
    <div style={current_display ? 'width:95%': ''}>
        <div id="display_text">
            {current_display}
        </div>
    </div>
</main>

<style lang="scss">
    @import "src/styles.scss";
    main {
       
        display: flex;
        align-items: end;
        justify-content: center;
        height: 10px;
        div {
            width: 100%;
            border-bottom: 1px solid $primary;
        }
    }

    #display_text {
        font-size: 30px;
        font-family: "Courier New", Courier, monospace;
        font-weight: bold;
        border: 0;
        margin-left: 20px;
        width: fit-content;
    }
</style>
