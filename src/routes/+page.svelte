<script>
	import { onMount } from 'svelte';

    let slideWidth=980;
    let slideHeight=552;
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
        return wrapperElement.clientHeight * slideAspectRatio / slideWidth;
    }

    onMount(() => {
        const resizeObserver = new ResizeObserver(() => {
            scale = computeScale();
        });
        resizeObserver.observe(wrapperElement);

        scale = computeScale();
    });
</script>
<div class="grid grid-cols-[1fr_max-content] w-screen h-screen p-5">
    <div class="w-full h-full" bind:this={wrapperElement}>
        <div style={`position: absolute; top: 50%; left: 50%; width: ${width}px; height:${height}px; transform: translate(-50%, -50%) scale(${scale}); border: 4px dashed #aaa;`}>
            <h2>Titre slide 1</h2>
        </div>
    </div>
</div>
<div class="hidden">
    <h2>Titre slide 2</h2>
</div>
