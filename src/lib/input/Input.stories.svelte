<script>
	import { Meta, Template, Story } from '@storybook/addon-svelte-csf';
	import Input from './Input.svelte';
</script>

<Meta
	title="Components/Input"
	component={Input}
	argTypes={{
		label: { control: 'text' },
		value: { control: 'text' },
		placeholder: { control: 'text' },
		helperText: { control: 'text' },
		status: {
			options: ['success', 'error', 'warning', 'default'],
			control: 'select',
		},
		disabled: { control: 'boolean' },
		type: {
			options: ['text', 'password', 'email', 'number'],
			control: 'select',
		},
		textArea: { control: 'boolean' },
		rows: { control: 'number' },
	}}
/>

<Template let:args>
	<div class="inputComponents">
		<div>
			<Input inputId={'0x'} {...args} />
		</div>
	</div>
</Template>

<Story name="default" />
<Story
	name="Success"
	args={{
		status:"success"
	}}
/>
<Story name="Warning"
args={{
	status:"warning"
}} />
<Story name="Error"
args={{
	status:"error"
}} />

<Story name="Text Area"
args={{
	textArea:true
}} />

<style>
	.inputComponents {
		display: flex;
		flex-direction: row;
		justify-content: center;
		align-items: center;
		max-width: 1000px;
		flex-wrap: wrap;
		gap: 1rem;
		margin: auto;
	}
	.inputComponents div {
		width: 300px;
	}
</style>
