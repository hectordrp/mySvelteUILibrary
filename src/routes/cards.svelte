<script>
	import Card from '$lib/card/Card.svelte';
	import '../global.css';
</script>

<a href="/">Home</a>

<div class="cardComponents">

	<Card >
		<div slot="card-header" class="card-header">
			Card title
		</div>
		<div slot="card-body" class="card-body">
			Here goes the body of the card.
		</div>
	</Card>
	
	<Card cardImage={"https://i.picsum.photos/id/522/600/300.jpg?hmac=SubYDg-1RwFetIwgLOa5s8ER3dGn-xNVoqWCvUGQrTE"} >
		<div slot="card-header" class="card-header">
			Card with image
		</div>
		<div slot="card-body" class="card-body">
			Here goes the body of the card.
		</div>
		<div slot="card-footer" class="card-footer">
			<button>test button1</button>
			<button>test button2</button>
		</div>
	</Card>

	<Card hoverEffect={false}>
		<div slot="card-header" class="card-header">
			No hover effect.
		</div>
		<div slot="card-body" class="card-body">
			This card does not have a hover effect.
		</div>
	</Card>

	<Card >
		<div slot="card-header" class="card-header">
			Card title
		</div>
		<div slot="card-body" class="card-body">
			<div class="subTitle">Secondary text</div>
			<div>Lorem ipsum dolor sit amet, consectetur adipiscing elit.</div>
			
		</div>
	</Card>

	<Card cardImage={"https://i.picsum.photos/id/869/600/600.jpg?hmac=KPHeIFwjCti8IobZHNVQHsLGdw2CWlVoHuEkU77T4c0"} hasGradient={true}>
		<div slot="card-header" class="card-header">
			Card title
		</div>
		<div slot="card-body" class="card-body">
			Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec vitae mauris dolor. Sed dapibus metus in mollis pellentesque. 
			<br> Donec interdum interdum enim imperdiet euismod. 
			<br>
			<br> Integer auctor mi tellus, ac suscipit nibh porta porttitor. Phasellus eu vestibulum felis. In et vulputate tortor. 
		</div>
	</Card>
</div>

 
<style>
	.cardComponents {
		display: grid;
        grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
        grid-gap: 1rem;
        margin: 2rem auto;
		max-width: 1000px;
		align-items: center;
	}

	.card-header {
		font-size: 1.2rem;
		font-weight: 600;
		color: var(--atos-blue);
	}

	.card-body {
		font-size: 0.8rem;
		font-weight: 400;
		color: var(--atos-light-gray);
	}

	.subTitle {
		font-size: 1rem;
		font-weight: 400;
		color: var(--atos-light-gray);
		margin-bottom: 0.2rem;
	}


</style>
