<script>
	import Image from '$lib/image/Image.svelte';
	import '../global.css';
</script>

<a href="/">Home</a>

<div class="imagesContainer">
	<div class="image">
		<Image > 
			<div slot="image-text" class="image-text">Here goes the client need in Relaway Regular</div>
		</Image>
	</div>	
	<div class="image" style="min-width: 500px">
		<Image textBox={true} > 
			<div slot="image-text" class="image-sideText">Here goes the client need in Relaway Regular</div>
		</Image>
	</div>	
	<div class="image">
		<Image gradientDirection={"to left"}> 
			<div slot="image-text" class="image-text" style="font-weight: 700;">Gradient to left</div>
		</Image>
	</div>	
	<div class="image">
		<Image gradientDirection={"to right"}> 
			<div slot="image-text" class="image-text" style="font-weight: 700;"> Gradient to right</div>
		</Image>
	</div>	
	<div class="image">
		<Image gradientDirection={"to top"}> 
			<div slot="image-text" class="image-text" style="font-weight: 700; color: white">Gradient to top</div>
		</Image>
	</div>		
</div>

<style>
	.imagesContainer {
		display: flex;
		justify-content: center;
		flex-wrap: wrap;
		align-items: center;
		height: 100%;
		width: 100%;
		gap: 1rem;
		align-items: stretch;
	}
	.image {
		min-height: 400px;
		min-width: 300px;
	}

	.image-text {
		padding: 1rem;
		font-size: 1.5rem;
		box-sizing: border-box;
		width: min-content;
		font-weight: 400;
		min-width: 100%;
		color: var(--atos-black);
    }

	.image-sideText {
		padding: 1rem;
		font-size: 1.5rem;
		box-sizing: border-box;
		width: min-content;
		font-weight: 400;
		min-width: 60%;
		color: var(--atos-white);
    }
</style>
