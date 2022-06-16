<script>
	import { Meta, Template, Story } from '@storybook/addon-svelte-csf';
	import Input from './Input.svelte';
</script>

<Meta
	title="Components/Input/InputsOverview"
	component={Input}
	argTypes={{
        label: { control: 'text' },
        value: { control: 'text' },
        placeholder: { control: 'text' },
        helperText: { control: 'text' },
        status: {options: ["success", "error", "warning", "default"], control: 'select'},
        disabled: { control: 'boolean' },
        type: {options: ["text", "password", "email", "number"], control: 'select'},
        textArea: { control: 'boolean' },
        rows: { control: 'number' }
	}}
/>

<Template let:args>
	<div class="inputComponents">
		<div>
			<Input inputId={'0x'} {...args} />
		</div>
		<div>
			<Input inputId={'0'} />
		</div>
		<div>
			<Input inputId={'1'} status={'success'} autocapitalize={true} />
		</div>
		<div>
			<Input inputId={'2'} status={'warning'} />
        </div>

        <div>
            <Input inputId={'3'} status={'error'} />
        </div>
        <div>
            <Input inputId={'5'} disabled={true} value={'This input is disabled'}/>
        </div>
        <div>
            <Input inputId={'4'} status={''} textArea={true} />
        </div>
	</div>
</Template>


<Story name="default" />

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
