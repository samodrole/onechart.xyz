<script>
    import Image from './Image.svelte'
    export let cardinfo;

</script>

<div class="card">
    <a class="thumbnail" href={cardinfo.link} target="_blank" rel="noreferrer">

        <div class="image">
            <Image src="./images/mostF1wins.jpeg" alt={cardinfo.alt}/>
        </div>
        <div class="cardinfo">
            <h3>{cardinfo.title}</h3>
            <p>{cardinfo.year} / {cardinfo.month}</p>
        </div>

    </a>
</div>