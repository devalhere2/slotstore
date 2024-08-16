<script>
    import Dropdown from "./Dropdown.svelte";
</script>

<div id="button_bar">
    <button id="dropdown">
        <div id="text">
            New
        </div>
        <img src="/down_arrow.svg" alt="" width="10px">
    </button>
    <button id="dropdown">
        <div id="text">
            New
        </div>
        <img src="/down_arrow.svg" alt="" width="10px">
    </button>
    <Dropdown />
 
</div>


<style lang="scss">
    #button_bar {
        display: flex;
        align-items: center;
        justify-content: start;
        
    }
#dropdown{
    height: 30px;
    padding: 0px 10px;
    display: flex;
    align-items: center;
    justify-content: center;
    margin-left: 10px;
    border: 1px solid black;
    border-radius: 50px;
    #text {
        margin-right: 5px;
    }
}
</style>