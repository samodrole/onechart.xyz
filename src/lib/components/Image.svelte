<script>
    import { onMount } from 'svelte'
    export let src;
    export let alt;

    let loaded = false;
    let failed = false;
    let loading = false;

    onMount(() => {
        const img = new Image();
        img.src = src;
        loading = true;

        img.onload = () => {
                loading = false;
                loaded = true;
        };
        img.onerror = () => {
                loading = false;
                failed = true;
        };
    })
</script>


{#if loaded}
	<img {src} {alt} />
{:else if failed}
	<img src="http://onechart.xyz/images/noImage.png" alt="Not Found"/>
{/if}


<style>
    img {
        width: 100%;
        height: 100%;
        display:block;
    }
</style>

