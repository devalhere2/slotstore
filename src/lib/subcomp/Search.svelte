<div id="sbar"> 
    <form class="search-form">   
        <div class="relative">
            <svg class="search-icon" aria-hidden="true" fill="None" viewBox="0 0 20 20">
                <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="m19 19-4-4m0-7A7 7 0 1 1 1 8a7 7 0 0 1 14 0Z"/>
            </svg>
            <input type="search" id="default-search" placeholder="Search Elements, Components ..." required autocomplete="off"/>
            <button type="submit" class="">Search</button>
        </div>
    </form>
</div>

<style lang="scss">
    @import 'src/styles.scss';

    #sbar {
        height: 60px;
        display: flex;
        align-items: center;
        justify-content: center; /* Center the form horizontally */
        padding: 0 10px;
        
        
    }

    .search-form {
        width: 100%;
        display: flex;
        justify-content: center; /* Center the form content */
    }

    .relative {
        position: relative;
        display: flex;
        align-items: center;
        width: 50%; /* Adjust width as needed */
    }

    .search-icon {
        position: absolute;
        left: 10px;
        width: 16px;
        height: 16px;
        pointer-events: none;
    }

    input[type="search"] {
        width: 100%;
        padding: 8px 8px 8px 36px; /* Add padding to the left to make space for the icon */
        border: 1px solid gray;
        border-radius: 5px;
        font-weight: bold;
        font-size: 16px;
        font-family: 'Courier New', Courier, monospace;
        &:focus {
            outline: 1px solid $primary;
            outline-offset: -1px;
            border-color: $primary;
        }
        
    }

    button {
        margin-left: 10px;
        padding: 8px 16px;
        border: none;
        border-radius: 4px;
        background-color: $primary;
        color: $secondary;
        font-weight: bold;
        font-size: 16px;
        cursor: pointer;
        font-family: 'Courier New', Courier, monospace;
        &:focus {
            outline: none;
        }
        
    }
</style>