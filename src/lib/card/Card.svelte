<script lang="ts">
    export let cardImage: string = ''; 
    // https://i.picsum.photos/id/869/600/600.jpg?hmac=KPHeIFwjCti8IobZHNVQHsLGdw2CWlVoHuEkU77T4c0
    // https://i.picsum.photos/id/522/600/300.jpg?hmac=SubYDg-1RwFetIwgLOa5s8ER3dGn-xNVoqWCvUGQrTE
    export let minImgHeight: string = '100px'; // min height of image, in pixels (100px).
    export let hasGradient: boolean = false; // if true, the card image will have a gradient background.
    export let hoverEffect: boolean = true; // if true, the card image will have a hover effect.
</script>

<div class="cardContainer { hoverEffect  ? "hoverEffect" : ""}">
    {#if cardImage}
        <div class="cardImg"  style="background-image: { hasGradient ? "linear-gradient(226deg, var(--atos-black) , transparent 60%)," : ""} url({cardImage}); min-height:{minImgHeight};"/>
    {/if}
    <div class="card" style={!cardImage ? "border-radius: 20px;" : ""}>
        <slot name="card-header" class="card-header" > </slot>
        <slot name="card-body" class="card-body"> </slot>
        
        <slot name="card-footer" class="card-footer"></slot>
        
    </div>
</div>

<style>
    .cardContainer {
        width: 100%;
        border-radius: 20px;
    }
    .card {
        color: #fff;
        display: flex;
        flex-direction: column;
        justify-content: flex-start;
        min-width: 150px;
        min-height: 100px;
        width: 100%;
        height: 100%;
        background-color: var(--atos-gray);
        border-radius: 0px 0px 20px 20px;
        align-items: stretch;
        gap: 0.5rem;
        padding: 10px 15px;
        box-sizing: border-box;
        
    }
    .cardContainer.hoverEffect:hover {
        box-shadow: 0px 0px 10px var(--atos-blue);
    }

    .cardImg {
        min-height: 100px;
        width: 100%;
        background-position: center;
        background-size: cover;
        background-repeat: no-repeat; 
        border-radius: 20px 20px 0px 0px;

    }

    @media (min-width: 768px) {
        .cardImg {
            /* min-height: 200px; */
        }
    }

</style>