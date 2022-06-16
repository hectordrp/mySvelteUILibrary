<script lang="ts">
	//Input UI copmonent

	export let inputId: string = 'input-id';
	export let label: string = 'Label';
	export let value: string = '';
	export let placeholder: string = 'Placeholder';
	export let helperText: string = 'Helper Text';
	export let status: "success" | "error" | "warning" | "" = '';
    export let disabled: boolean = false;
    export let required: boolean = false;
    export let type: "text" | "password" | "email" | "number" | "tel" | "url" | "search" | "date" | "time" | "datetime-local" | "month" | "week" | "color" | "file" | "range" = 'text';
    export let textArea: boolean = false;
    export let rows: number = 4;


    
</script>

<div class="customInput {status}">
	<label for="inputId">
		{label}
	</label>
	<div class="inputContainer">
        {#if textArea}
            <textarea id={inputId} name={inputId} {type} {value} {placeholder} {disabled} {required} {rows}></textarea>
        {:else}
		    <input id={inputId} name={inputId} {type} {value} {placeholder} {disabled} {required}/>
        {/if}

        <div class="statusIcon">
            <div class="statusIcon--{status}"></div>
        </div>
	</div> 
	<small>
		{helperText}
	</small>
</div>

<style>
	label {
		display: block;
		margin-bottom: 0.5rem;
	}
    small {
        margin-left: 20px;
    }
    .inputContainer {
        display: flex;
        
        border-radius: 20px;
        justify-content: center;
        align-items: center;
        background-color: var(--atos-gray);
        padding: 0px 10px;
    }
	input, textArea {
		width: 100%;
        border-radius: 20px;
		padding: 0.5rem;
        background: transparent;
        border: none;
        outline: none;
        color: lightgray;
        box-sizing: border-box;
        border: 3px solid transparent;
	}

    .customInput {
        width: 100%;
    }

	/* error */
	.customInput.error {
        color: var(--atos-red);
	}
	.customInput.error .inputContainer {
		border: 3px solid var(--atos-red);
	}

	/* success */
    .customInput.success {
        color: var(--atos-green);
	}
	.customInput.success .inputContainer {
		border: 3px solid var(--atos-green);
	}

	/* warning */
    .customInput.warning {
        color: var(--atos-yellow);
	}
	.customInput.warning .inputContainer {
		border: 3px solid var(--atos-yellow);
	}

    .statusIcon {
        padding: 0.5rem;
    }
</style>
