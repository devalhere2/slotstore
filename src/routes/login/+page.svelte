<script>
    let type = "login";
    const activeStyle =
        "border-top: 2px solid #001524; border-left: 2px solid #001524; border-right: 2px solid #001524; box-sizing: border-box;";
</script>

<main>
    <!-- <form action="">
            <input type="text" name="" id="" placeholder="Enter Username">
            <br>
            <input type="password" name="" id="" placeholder="Enter Password">
            <br>
            <button>Login</button>            
        </form> -->

    <div id="type_bar">
        <button
            on:click={() => (type = "login")}
            style={type === "login" ? activeStyle : ""}>Login</button
        >
        <button
            on:click={() => (type = "create")}
            style={type === "create" ? activeStyle : ""}>Create</button
        >
    </div>
    <div id="formdisplay">
        {#if type === "login"}
            <form action="">
                <input type="text" name="" id="" placeholder="Enter Username ..." />
                <br />
                <input
                    type="password"
                    name=""
                    id=""
                    placeholder="Enter Password ..."
                />
                <br />
                <button>Login</button>
            </form>
        {:else}
            <form action="">
                <input type="text" name="" id="" placeholder="Enter Username ..." />
                <br />
                <input
                    type="password"
                    name=""
                    id=""
                    placeholder="Enter Password ..."
                />
                <br />
                <input
                    type="password"
                    name=""
                    id=""
                    placeholder="Confirm Password ..."
                />
                <br />
                <button>Create</button>
            </form>
        {/if}
    </div>
</main>

<style lang="scss">
    @import "src/styles.scss";
    main {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        height: calc(100vh - 60px);
    }
    #formdisplay {
        background-color: lightcyan;
        min-height: 100px;
        width: 400px;
        border: 2px solid $primary;
        box-sizing: border-box;
        display: flex;
        align-items: center;
        justify-content: center;
        border-bottom-left-radius: 10px;
        border-bottom-right-radius: 10px;
    }
    form {
        box-sizing: border-box;

        input {
            box-sizing: border-box;
            width: 360px;
            margin-top: 20px;
            border: 2px solid $primary;
            border-radius: 5px;
            font-size: 16px;
            font-family: 'Courier New', Courier, monospace;
            font-weight: bold;
            color: $primary;
            padding: 10px;
        }
        input::placeholder {
            color: $primary;
        }
        button {
            width: 360px;
            margin: 20px 0px;
            height: 40px;
            color: $primary;
            border: 2px solid $primary;
            background-color: $secondary;
            font-family: 'Courier New', Courier, monospace;
            font-size: 16px;
            font-weight: bold;
            border-radius: 5px;
            &:focus {
                outline: 2px solid blueviolet;
                outline-offset: -2px;
                text-decoration: underline;
                border: 0;
            }
        }
    }
    #type_bar {
        display: flex;

        button {
            font-family: "Courier New", Courier, monospace;
            font-size: 16px;
            font-weight: bold;
            cursor: pointer;
            width: 200px;
            border-radius: 0;
            background-color: $secondary;
            color: $primary;
            border: 0;
            border-top-left-radius: 10px;
            border-top-right-radius: 10px;

            height: 30px;
            margin: 0;
            &:hover {
                text-decoration: underline;
            }
        }
    }
    
</style>
