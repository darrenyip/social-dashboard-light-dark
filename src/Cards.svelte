<script>
    import App from "./App.svelte";
    import Card from "./Card.svelte";
    let info = [
        {
            brand: "facebook",
            followers: "1987",
            flex_number: "12",
            up_or_down: true,
        },
        {
            brand: "twitter",
            followers: "1044",
            flex_number: "99",
            up_or_down: true,
        },
        {
            brand: "instagram",
            followers: "11k",
            flex_number: "1099",
            up_or_down: true,
        },
        {
            brand: "youtube",
            followers: "8239",
            flex_number: "144",
            up_or_down: false,
        },
    ];
</script>

<style type="text/scss">
    .cards-container{
        padding: 0 24px;
    }
    @media (min-width:1200px){
        .cards-container{
            display: grid;
            grid-template-columns: repeat(4,1fr);
            grid-column-gap: 30px;
            width: 1110px;
            padding: 0;
            // padding: 0 165px;
        }
    }
</style>

<div class="cards-container">
    {#each info as cardInfo}
        <Card {...cardInfo} class="card"/>
    {/each}
</div>
