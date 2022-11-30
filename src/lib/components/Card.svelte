<script>
    import Image from './Image.svelte'
    export let cardinfo;

</script>

<div class="card">
    <a class="thumbnail" href={cardinfo.link} target="_blank" rel="noreferrer">

        <div class="image">
            <Image src={cardinfo.image} alt={cardinfo.alt}/>
        </div>
        <div class="cardinfo">
            <h3>{cardinfo.title}</h3>
            <p>{cardinfo.year} / {cardinfo.month}</p>
        </div>

    </a>
</div>

<style>
    .card {
        transition: all .25s;
    }
    .card > a {
        display: block;
        color: var(--textColor100);
        text-decoration: none;
    }
    .card .image {
        position: relative;
        z-index: 0;
        width: 100%;
        height: 100%;
        min-height: 260px;
        min-width: 220px;
        padding: 2px;
        border: 1px solid #d1d1d1;
        border-radius: 8px;
        overflow: hidden;
        transition: box-shadow ease 0.25s;
        background: url('$lib/assets/Rhombus.gif') center no-repeat;
        background-size: 32px;
        transition: all .25s;

    }
    .card .image::after {
        content: "";
        position: absolute;
        z-index: 1;
        top: 0;
        right: 0;
        bottom: 0;
        left: 0;
    }
    .card > a:hover .image {
        box-shadow: 0 2px 16px 2px rgba(112, 112, 112, 0.4);
    }
    .cardinfo {
        padding: 0 8px;
    }
    .cardinfo p {
        color: var(--textColor40);
    }   


</style>