<script>
	import '../../app.css';
	import { flip } from 'svelte/animate';
	import { fly } from 'svelte/transition';
	import { notifications } from './notifications.js';

	export let themes = {
		danger: '#E26D69',
		success: '#84C991',
		warning: '#f0ad4e',
		info: '#5bc0de',
		default: '#aaaaaa'
	};
</script>

<div class="flex justify-center h-16 bg-primary">
	<div class="notifications">
		{#each $notifications as notification (notification.id)}
			<div animate:flip class="toast bg-secondary" transition:fly={{ y: 300 }}>
				<div class="content bg-secondary-contents">{notification.message}</div>
				{#if notification.icon}<i class={notification.icon} />{/if}
			</div>
		{/each}
	</div>
</div>

<style>
	/* .notifications {
		position: fixed;
		top: 10px;
		left: 0;
		right: 50px;
		margin: 0 auto;
		padding: 0;
		z-index: 9999;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		pointer-events: none;
	} */

	.toast {
		position: fixed;
		left: 50%;
		bottom: 35px;
		transform: translate(-50%, -50%);
		margin: 0 auto;
	}

	.content {
		padding: 10px;
		display: block;
		font-weight: 500;
	}
</style>
