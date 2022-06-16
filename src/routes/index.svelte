<script>
	import { First } from '$lib';
	import Input from '$lib/input/Input.svelte';
	import '../global.css';
</script>

<First name="World" textColor="yellowgreen" />
<div class="inputComponents">
	<Input inputId={"0"} />
	<Input inputId={"1"} status={"success"} autocapitalize={true}/>
	<Input inputId={"2"} status={"warning"}/>
	<Input inputId={"3"} status={"error"}/>
	<Input inputId={"4"} status={""} textArea={true}/>
	<Input inputId={"5"} disabled={true} value={"This input is disabled"}/>

</div>


<style>
	.inputComponents {
		display: flex;
		flex-direction: row;
		justify-content: center;
		align-items: center;
		max-width: 400px;
		flex-wrap: wrap;
		gap: 1rem;
		margin: auto;
	}
</style>
