<script lang="ts">
</script>

<header>
    <!-- <div class="navContainer"> -->
        <slot name="header-nav" class="header-nav"></slot>
    <!-- </div> -->
    <!-- pepe -->
</header>

<style>
    header {
        box-shadow: 0 .125rem .25rem rgba(0,0,0,.075);
        position: fixed;
        top: 0;
        right: 0;
        left: 0;
        z-index: 110;
        height: 60px;
        background-color: white;
        color: black;
    }

    header :global(.header-nav) {
        height: 100%;
        max-width: 1140px;
        margin: auto;
        display: flex;
        flex-direction: row; 
        flex-wrap: nowrap;
        align-items: center;
        justify-content: space-between;   
    }
</style>
