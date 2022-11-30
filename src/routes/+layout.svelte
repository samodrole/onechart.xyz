<script>
    import './styles.css';
    let width;
    // $: console.log(width)

</script>


<main bind:clientWidth={width}>
    {#if width < 660}
        <header>
            <div class="title">
                <h1><span class="logo"></span>onechart</h1>
            </div>
        </header>
    {:else}
        <aside>
            <div class="title">
                <h1><span class="logo"></span>onechart</h1>
                <p>A chart is a graphical representation for data visualization, in which "the data is represented by symbols, such as bars in a bar chart, lines in a line chart, or slices in a pie chart".</p><br/>
                <p>Charts are often used to ease understanding of large quantities of data and the relationships between parts of the data. Charts can usually be read more quickly than the raw data. <br/><br/><span>- Wikipedia</span></p>
            </div>
        </aside>
    {/if}

    <content>
        <slot></slot>
    </content>

</main>

<style>
    main {
        display: grid;
        align-items: start;
        grid-template-columns: 300px 1fr;
        flex-wrap: nowrap;
    }
    aside {
        padding: 24px 48px;
        position: sticky;
        top: 0;
        align-self: start;

    }
    .title h1 {
        margin-bottom: 24px;
    }
    .title p {
        color: var(--textColor80);
    }
    .title p span {
        font-style: italic;
        color: var(--textColor40);
    }
    .logo {
        width: 36px;
        height: 25px;
        margin-right: 8px;
        margin-bottom: -5px;
        display: inline-block;
        background-size: contain;
        background-image: url('$lib/assets/onechart-dark.svg');
        background-repeat: no-repeat;
    }
    content {
        display: grid;
        grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
        row-gap: 42px;
        column-gap: 24px;
        padding: 24px;
    }

    @media (max-width:660px) {
        main {
            grid-template-columns: 1fr;
        }
        content {
            padding: 16px;
        }
        header {
            display: flex;
            flex-direction: row;
            padding: 4px 16px;
            background: rgba(255, 255, 255, .6);
            border-bottom: 1px solid rgba(0, 0, 0, .1);;
            position: sticky;
            z-index: 10;
            top: 0;
            align-self: start;
            backdrop-filter: blur(20px);
            justify-content: space-between;
            align-items: center;
        }
        header .title h1 {
            margin: 1rem 0;
        }
        h1 {
            font-size: 1.8rem;
        }
        .logo {
            width: 28px;
            height: 20px;
        }

    }

</style>