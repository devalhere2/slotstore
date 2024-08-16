<script>
    import { onMount } from "svelte";
    import { goto } from "$app/navigation";
</script>

<!-- svelte-ignore a11y-click-events-have-key-events -->
<!-- svelte-ignore a11y-no-static-element-interactions -->

<nav lang="html">
    <div id="sitename" on:click={()=>goto('/')}>
        <div id="name">&lt;slotStore/&gt;</div>
    </div>
    <div id="buttons">
        <div id="login" on:click={()=>goto('/login')}>Login</div>
        <div id="join" on:click={()=>goto('/join')}>Join</div>
    </div>
</nav>

<slot />

<style lang="scss">
    @import 'src/styles.scss';
    nav {
        height: 60px;
        display: flex;
        font-weight: bolder;
        align-items: center;
        font-family: "Courier New", Courier, monospace;
        border-bottom: 2px solid $primary;
        box-sizing: border-box;
        #sitename {
            flex: 1;
            margin-left: 10%;
            display: flex;
            #name {
                cursor: pointer;
                font-size: 20px;
                color: $primary;
            }      
        }
        #buttons {
            display: flex;
            margin-right: 10%;
            #login, #join {
                margin-left: 10px;
                padding: 5px 10px;

                font-weight: bold;
            }
            #login {
                color: $primary;
                border: 1px solid $primary;
                border-radius: 5px;
                cursor: pointer;
                &:hover {
                    background-color: $secondary;
                }
            }
            #join {
                color: whitesmoke;
                border: 1px solid black;
                border-radius: 5px;
                cursor: pointer;
                background-color: $primary;
                &:hover {
                    color: $secondary;
                }
            
            }
            
        }
    }
</style>
