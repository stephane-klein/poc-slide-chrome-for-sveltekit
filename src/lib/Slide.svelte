<script>
	import { onMount } from 'svelte';

    let slideWidth=1600;
    let slideHeight=800;
    let width;
    let height;
    let scale;
    let wrapperElement;
    let slideAspectRatio;
    let screenAspectRatio;

    function computeScale() {
        slideAspectRatio = slideWidth / slideHeight;
        screenAspectRatio = wrapperElement.clientWidth / wrapperElement.clientHeight;
        width = slideWidth;
        height = slideHeight;
        return wrapperElement.clientHeight * (slideAspectRatio < screenAspectRatio ? slideAspectRatio : screenAspectRatio) / slideWidth;
    }

    onMount(() => {
        const resizeObserver = new ResizeObserver(() => {
            scale = computeScale();
        });
        resizeObserver.observe(wrapperElement);

        scale = computeScale();
    });
</script>
<div class="w-full h-full" bind:this={wrapperElement}>
    <div style={`position: absolute; top: 50%; left: 50%; width: ${width}px; height:${height}px; transform: translate(-50%, -50%) scale(${scale}); border: 2px dashed #eee;`}>
        <slot />
    </div>
</div>
