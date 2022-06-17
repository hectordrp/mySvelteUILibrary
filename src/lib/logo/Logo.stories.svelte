<script>
	import { Meta, Template, Story } from '@storybook/addon-svelte-csf';
	import Logo from './Logo.svelte';
</script>

<Meta
	title="Components/Logo"
	component={Logo}
    argTypes={{
        subText: { control: 'text' }
    }}
/>

<Template let:args>
	<Logo {...args}/>
</Template>

<Story 
    name="default"
/>
