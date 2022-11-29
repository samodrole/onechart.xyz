<script>
    import Card from '$lib/components/Card.svelte'
    import {data} from '$lib/assets/data.js'

</script>

<svelte:head>
    <title>onechart</title>
    <meta name="description" content="onechart at a time" />
</svelte:head>



{#each data as card}
    <Card cardinfo={card}/>
{/each}