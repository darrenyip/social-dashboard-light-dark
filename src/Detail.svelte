<script>
    export let title;
    export let brand;
    export let number;
    export let up_or_down;
    export let percent;
</script>

<style type="text/scss">
    .detail-container {
        background: var(--card-bg);
        transition: background 500ms ease-in-out;

        border-radius: 5px;
        margin-bottom: 16px;
        padding: 27px 31px 19px 24px;
    }
    .detail-header {
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin-bottom: 23px;
        p {
            font-style: normal;
            font-weight: bold;
            font-size: 14px;
            line-height: 17px;
            color: var(--text-2);
            transition:color 1000ms ease-in-out;

        }
    }
    .detail-footer {
        display: flex;
        justify-content: space-between;
        align-items: flex-end;
        .detail-number {
            font-style: normal;
            font-weight: bold;
            font-size: 32px;
            line-height: 39px;
            color: var(--text-1);
            transition:color 1000ms ease-in-out;

        }
        .arrow-percent {
            display: flex;
            align-items: center;
        }
    }
    .up {
        font-weight: bold;
        font-size: 12px;
        line-height: 15px;
        text-align: right;
        color: #1eb589;
    }
    .down {
        font-style: normal;
        font-weight: bold;
        font-size: 12px;
        line-height: 15px;
        text-align: right;
        color: #dc414c;
    }
    @media (min-width:1200px){
        .detail-container:hover{
            background-color: var(--hover);
        }
        .detail-container{
            box-sizing: border-box;
            width: 255px;
            height:125px;
            padding: 26px 31px 19px 24px;
            margin-bottom: 0px;
        }
    }
</style>

<div class="detail-container">
    <div class="detail-header">
        <p>{title}</p>
        {#if brand == 'facebook'}
            <img src="./images/icon-facebook.svg" alt="" />
        {/if}
        {#if brand == 'youtube'}
            <img src="./images/icon-youtube.svg" alt="" />
        {/if}
        {#if brand == 'twitter'}
            <img src="./images/icon-twitter.svg" alt="" />
        {/if}
        {#if brand == 'instagram'}
            <img src="./images/icon-instagram.svg" alt="" />
        {/if}
    </div>
    <div class="detail-footer">
        <p class="detail-number">{number}</p>
        <div class="arrow-percent">
            {#if up_or_down}
                <img
                    class="daliy-change-svg"
                    src="./images/icon-up.svg"
                    alt="" />
                <p class="up">{percent}</p>
            {:else}
                <!-- else content here -->
                <img
                    class="daliy-change-svg"
                    src="./images/icon-down.svg"
                    alt="" />
                <p class="down">{percent}</p>
            {/if}

        </div>
    </div>
</div>
