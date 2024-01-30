<script>
    import Slide from "$lib/Slide.svelte";
</script>
<Slide>
    <div class="slide-grid-layout">
        <div class="top-left">
            <slot name="top-left" />
        </div>
        <div class="top">
            <slot name="top" />
        </div>
        <div class="top-right">
            <slot name="top-right" />
        </div>
        <div class="main">
            <slot name="main" />
        </div>
        <div class="bottom-left">
            <slot name="bottom-left" />
        </div>
        <div class="bottom">
            <slot name="bottom" />
        </div>
        <div class="bottom-right">
            <slot name="bottom-right" />
        </div>
    </div>
</Slide>
<style>
    .slide-grid-layout {
        width: 100%;
        height: 100%;
        display: grid;
        grid-template-columns: auto 1fr auto;
        grid-template-rows: auto 1fr auto;
        grid-template-areas: "topleft top topright"
            "main main main"
            "bottomleft bottom bottomright";
    }

    .top-left {
        grid-area: topleft;
    }

    .top {
        grid-area: top;
    }

    .top-right {
        background-color: red;
        grid-area: topright;
    }

    .main {
        grid-area: main;
    }

    .bottom-left {
        grid-area: bottomleft;
    }

    .bottom {
        grid-area: bottom;
    }

    .bottom-right {
        background-color: green;
        grid-area: bottomright;
    }
</style>
