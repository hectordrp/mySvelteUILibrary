<script lang="ts">
	export let imageUrl: URL = new URL(
		'https://i.picsum.photos/id/1067/600/600.jpg?hmac=2d9VT4DylzR_0hHCz7MXYWIP7xOswDg689TD4MHCxuk'
	);
	export let minHeight: number = 0;
	export let minWidth: number = 0;
	export let textBox: boolean;
	export let gradientDirection: "to bottom" | "to right" | "to top" | "to left" = 'to bottom';

    let invertedGradientDirection = (): string => {
        switch (gradientDirection) {
            case 'to bottom':
                return 'to top';
            case 'to right':
                return 'to left';
            case 'to top':
                return 'to bottom';
            case 'to left':
                return 'to right';
        }
    };


</script>

<div class="customImage">
    {#if textBox}
        <slot name="image-text" class="image-text"></slot>
    {/if}

	<div
		class="imageContainer"
		style="
            background-image:  linear-gradient({invertedGradientDirection()}, var(--atos-black) , transparent 40%), linear-gradient({gradientDirection}, var(--atos-blue) , transparent 40%), url({imageUrl});  
            {minHeight ? `min-height: ${minHeight}px;` : ''} 
            {minWidth ? `min-width: ${minWidth}px;` : ''}"
	>
        {#if !textBox}
            <slot name="image-text" class="image-text"></slot>
        {/if}
    </div>
</div>

<style>
	.customImage {
		display: flex;
		justify-content: center;
		align-items: center;
		height: 100%;
		width: 100%;
        background-color: var(--atos-gray);
	}
	.imageContainer {
		width: 100%;
		height: 100%;
		background-size: cover;
		background-position: center;
		background-repeat: no-repeat;
	}

    
</style>
