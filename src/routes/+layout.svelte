<script lang="ts">
    import "$lib/tailwind.css";
    import Dots from "$lib/dots/dots.svelte";
</script>

<svelte:head>
    <title>Quado</title>
</svelte:head>

<main class="h-screen w-screen select-text overflow-hidden text-center bg-backgroundSecondary text-primary">
    <Dots />

    <div class="z-[1] relative">
        <slot />
    </div>
</main>
