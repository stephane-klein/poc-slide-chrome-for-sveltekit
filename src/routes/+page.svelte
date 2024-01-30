<script>
    // import Slide from "$lib/Slide.svelte";
    import SlideGridLayout from "$lib/SlideGridLayout.svelte";
    import Center from "$lib/Center.svelte";
</script>
<div class="grid grid-cols-[1fr_max-content] w-screen h-screen p-5">
    <!-- <Slide> -->
    <!--     <h2>Title 1</h2> -->
    <!-- </Slide> -->
    <SlideGridLayout>
        <span slot="main"><Center><h2 class="text-8xl">Title 2</h2></Center></span>
        <span slot="bottom-left"><img src="https://sklein.xyz/_app/immutable/assets/avatar.iAdKzKwE.avif" /></span>
    </SlideGridLayout>
</div>
