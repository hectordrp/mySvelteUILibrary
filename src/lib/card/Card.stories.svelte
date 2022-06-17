<script lang="ts">
	import { Meta, Template, Story } from '@storybook/addon-svelte-csf';
	import Card from './Card.svelte';
</script>

<Meta
	title="Components/Card"
	component={Card}

	
/>

<Template let:args>
    <div class="cardComponents">
        <Card {...args}>
            <div slot="card-header" class="card-header">
                {@html args.headerContent ? args.headerContent : ""}
            </div>
            <div slot="card-body" class="card-body">
                {#if args.bodySubtitle}
                    <div class="subTitle"> {args.bodySubtitle }</div>
                {/if}
                {@html args.bodyContent ? args.bodyContent : ""}
            </div>
        </Card>
    </div>
</Template>

<Story 
    name="default" 
    args={{
        headerContent: "Card title",
        bodyContent: `
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec vitae mauris dolor. Sed dapibus metus in mollis pellentesque. 
			<br> Donec interdum interdum enim imperdiet euismod. 
			<br>
			<br> Integer auctor mi tellus, ac suscipit nibh porta porttitor. Phasellus eu vestibulum felis. In et vulputate tortor. `,
        bodySubtitle: `Secondary text`
    }}
/>

<Story 
    name="With image" 
    args={{
        headerContent: "Card with image",
        bodyContent: `Here goes the body of the card.`,
        cardImage:"https://i.picsum.photos/id/522/600/300.jpg?hmac=SubYDg-1RwFetIwgLOa5s8ER3dGn-xNVoqWCvUGQrTE"
    }}
/>

<Story 
    name="With image and gradient" 
    args={{
        headerContent: "Card with image",
        bodyContent: `It also has a black gradient`,
        hasGradient: true,
        cardImage:"https://i.picsum.photos/id/522/600/300.jpg?hmac=SubYDg-1RwFetIwgLOa5s8ER3dGn-xNVoqWCvUGQrTE"
    }}
/>

<style>
    .cardComponents {
		display: grid;
        grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));  
        grid-gap: 1rem;
        margin: 2rem auto;
		max-width: 350px;
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