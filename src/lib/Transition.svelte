<script>
	import { cubicOut } from 'svelte/easing';
	export let key = '';

	const enter = (node, { delay = 270, duration = 230, easing = cubicOut, x = 0, y = 0, opacity = 0 } = {}) => {
    const style = getComputedStyle(node);
    const target_opacity = +style.opacity;
    const transform = style.transform === 'none' ? '' : style.transform;
    const od = target_opacity * (1 - opacity);
    return {
        delay,
        duration,
        easing,
        css: (t, u) => `
			transform: ${transform} translate(${(1 - t) * x}px, ${(1 - t) * y}px);
			opacity: ${target_opacity - (od * u)}`
    };
	}

	const exit = (node, { delay = 0, duration = 230, easing = cubicOut, x = 0, y = 0, opacity = 0 } = {}) => {
    const style = getComputedStyle(node);
    const target_opacity = +style.opacity;
    const transform = style.transform === 'none' ? '' : style.transform;
    const od = target_opacity * (1 - opacity);
    return {
        delay,
        duration,
        easing,
        css: (t, u) => `
			transform: ${transform} translate(${(1 - t) * x}px, ${(1 - t) * y}px);
			opacity: ${target_opacity - (od * u)}`
    };
	}
</script>

{ #key key }
	<main in:enter={{ y: -25 }} out:exit={{ y: -25 }}>
		<slot />
	</main>
{ /key }

<style>
	main {
		flex: 1;
		display: flex;
		flex-flow: column;
		justify-content: stretch;
		align-items: stretch;
	}
</style>