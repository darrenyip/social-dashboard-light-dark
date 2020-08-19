<script>
    import Detail from './Detail.svelte';
    let details = [
        {
            title:"Page Views",
            brand:"facebook",
            number:"87",
            up_or_down:true,
            percent:'3%'
        },
        {
            title:"Likes",
            brand:"facebook",
            number:"52",
            up_or_down:false,
            percent:'2%'
        },
        {
            title:"Likes",
            brand:"instagram",
            number:"5462",
            up_or_down:true,
            percent:'2257%'
        },
        {
            title:"Profile Views",
            brand:"instagram",
            number:"52k",
            up_or_down:true,
            percent:'1375%'
        },
        {
            title:"Retweets",
            brand:"twitter",
            number:"117",
            up_or_down:true,
            percent:'303%'
        },
        {
            title:"Likes",
            brand:"twitter",
            number:"507",
            up_or_down:true,
            percent:'553%'
        },
        {
            title:"Likes",
            brand:"youtube",
            number:"107",
            up_or_down:false,
            percent:'19%'
        },
        {
            title:"Total Views",
            brand:"youtube",
            number:"1407",
            up_or_down:false,
            percent:'12%'
        }
    ]
</script>

<style>
    @media (min-width:1200px){
        .details-container{
            box-sizing: border-box;
            display: grid;
            grid-template-columns: repeat(4,1fr);
            grid-column-gap: 30px;
            grid-row-gap: 24px;
            padding: 0;
            width: 1110px;
        }
    }
</style>

<div class="details-container">
    {#each details as detail}
        <Detail {...detail}/>
    {/each}
</div>