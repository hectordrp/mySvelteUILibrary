<script>
	import { Meta, Template, Story } from '@storybook/addon-svelte-csf';
	import Image from './Image.svelte';
</script>

<Meta
	title="Components/Image"
	component={Image}
    argTypes={{
        imageUrl: { control: 'text' },
        width: { control: 'number' },
        height: { control: 'number' },
        text: { control: 'text' },
        gradientDirection: { options: ["to bottom", "to right", "to top", "to left"], control: 'select' },
        textBox: { control: 'boolean' },
    }}
    args={{
        imageUrl: 'https://i.picsum.photos/id/1067/600/600.jpg?hmac=2d9VT4DylzR_0hHCz7MXYWIP7xOswDg689TD4MHCxuk',
        
    }}
	
/>

<Template let:args>
	<div class="imagesContainer">
        <div class="image" style="{args.imageStyle ? args.imageStyle : ""}">
            <Image {...args}> 
                <div slot="image-text" class=" {args.customClass ? "image-sideText" : "image-text"}">{args.text}</div>
            </Image>
        </div>	
    </div>
</Template>

<Story 
    name="default" 
    args={{
        text: '',
        gradientDirection: 'to bottom',
    }} 
/>
<Story
	name="With text"
	args={{
		text: 'Here goes the client need in Relaway Regular',
        gradientDirection: 'to bottom',
	}}
/>

<Story
	name="With outer text"
	args={{
		text: 'Here goes the client need in Relaway Regular',
        gradientDirection: 'to bottom',
        textBox: true,
        customClass: 'image-sideText',
        imageStyle: "min-width: 600px;"
	}}
/>

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