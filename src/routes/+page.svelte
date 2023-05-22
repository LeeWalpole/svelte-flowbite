<script>
	import { Button, Modal } from 'flowbite-svelte';
	let modal1 = false;
	let modal2 = false;
</script>

<button on:click={() => (modal1 = true)}>Open Modal 1</button>

<Modal id="modal1" title="Modal 1" bind:open={modal1} autoclose outsideclose>
	<h1 class="text-base leading-relaxed text-gray-500 dark:text-gray-400">Modal 1</h1>

	<button on:click={() => (modal2 = true)}>Open Modal 2</button>

	<svelte:fragment slot="footer">
		<Button on:click={() => alert('Handle "success"')}>I accept</Button>
		<Button color="alternative">Decline</Button>
	</svelte:fragment>
</Modal>

<Modal id="modal2" title="Modal 2" bind:open={modal2} autoclose outsideclose>
	<button on:click={() => (modal2 = false)}>Close Modal 2</button>
</Modal>

<h1>Body here</h1>
