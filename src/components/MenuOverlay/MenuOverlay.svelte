<script lang="ts">
	import { onMount } from 'svelte';
	import Logo from './Logo.svelte';
	import SocialLinks from './SocialLinks.svelte';
	import NavMenu from './NavMenu.svelte';
	import handleResize from '../../utils/handleResize';
	import type { ScreenSize } from '../../utils/handleResize';

	let screenSize: ScreenSize;
	let isHidden = true;

	onMount(() => {
		const cleanup = handleResize((size) => {
			screenSize = size;
		});

		return cleanup;
	});

	const hideMenuOverlay = () => {
		isHidden = true;
	};
</script>

<div
	class="flex flex-col justify-between w-full h-screen bg-violet-500 absolute"
	class:hidden={isHidden}
>
	<div class="flex">
		<!-- {#if screenSize === 'xs'}
			<Logo />
		{/if} -->
		<div />
		<div on:click={hideMenuOverlay}>X</div>
	</div>

	<div class="flex justify-between items-center">
		<NavMenu />
		<Logo />
		<div>LOGO</div>
	</div>

	<SocialLinks />
</div>
