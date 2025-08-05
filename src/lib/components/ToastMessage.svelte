<script lang="ts">
	import type { Toast } from '../core/types';

	interface Props {
		toast: Toast;
	}

	let { toast }: Props = $props();
</script>

<div {...toast.ariaProps}>
	<div id="status" class="message">
		{#if typeof toast.message === 'string'}
			{toast.message}
		{:else}
			<toast.message {toast} {...toast.props} />
		{/if}
	</div>
</div>

<style>
	.message {
		display: flex;
		justify-content: center;
		margin: 4px 10px;
		color: inherit;
		flex: 1 1 auto;
		white-space: pre-line;
	}
</style>
