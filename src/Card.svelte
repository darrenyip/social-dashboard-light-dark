<script>
    export let brand;
    export let followers;
    export let flex_number;
    export let up_or_down;
    export let name = "@nathanf";
</script>

<style type="text/scss">
    .card-container {
        background: var(--card-bg);
        transition: background 500ms ease-in-out;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-content: center;
        padding: 32px 0 24px 0;
        margin-bottom: 24px;
    }
    .card-border-twitter {
        position: relative;
        padding-top: 4px;
        background-color: #178ff5;
        border-radius: 5px;
    }
    .card-border-facebook {
        position: relative;
        padding-top: 4px;
        background-color: #178ff5;
        border-radius: 5px;
    }
    .card-border-instagram {
        position: relative;
        background: linear-gradient(
            225deg,
            #df4896 0%,
            #ee877e 50.91%,
            #fdc366 100%
        );
        border-radius: 5px;
        padding-top: 4px;
    }
    .card-border-youtube {
        position: relative;
        padding-top: 4px;
        border-radius: 5px;
        background: #c4032b;
    }
    .card-header {
        display: flex;
        justify-content: center;
        align-items: center;
        margin-bottom: 28px;
        .logo {
            margin-right: 8px;
        }
        .name {
            p {
                font-style: normal;
                font-weight: bold;
                font-size: 12px;
                line-height: 15px;
                color: var(--text-1);
                transition: color 1000ms ease-in-out;

            }
        }
    }
    .followers {
        margin-bottom: 25px;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-content: center;
        &-number {
            font-style: normal;
            font-weight: bold;
            font-size: 56px;
            line-height: 48px;
            text-align: center;
            letter-spacing: -2px;
            color: var(--text-2);
            transition: color 1000ms ease-in-out;
            margin-bottom: 9px;
        }
        &-text {
            font-style: normal;
            font-weight: normal;
            font-size: 12px;
            line-height: 15px;
            text-align: center;
            letter-spacing: 5px;
            text-transform: uppercase;
            color: #8c98c6;
        }
    }
    .daily-change {
        display: flex;
        justify-content: center;
        align-content: center;
        p {
            margin-left: 4px;
        }
    }
    .daliy-change-svg {
        width: 10px;
        height: 10px;
        transform: translateY(3px);
    }
    .up {
        font-style: normal;
        font-weight: bold;
        font-size: 12px;
        line-height: 15px;
        color: #1eb589;
    }
    .down {
        font-style: normal;
        font-weight: bold;
        font-size: 12px;
        line-height: 15px;
        color: #dc414c;
    }

    @media (min-width: 1200px) {
        .card-container:hover{
            background-color: var(--hover);
        }
        .card-border-twitter {
            width:255px;
            height:216px;
            .up{
                margin-bottom: 1px;
            }
            .down{
                margin-bottom: 1px;
            }
        }
        .card-border-facebook {
            width:255px;
            height:216px;
        }
        .card-border-instagram {
            width:255px;
            height:216px;
        }
        .card-border-youtube {
            width:255px;
            height:216px;
        }
    }
</style>

<div class="card-border-{brand}">
    <div class="card-container">
        <div class="card-header">
            <div class="logo">
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
            <div class="name">
                <p>{name}</p>
            </div>
        </div>
        <div class="followers">
            <p class="followers-number">{followers}</p>
            <p class="followers-text">FOLLOWERS</p>
        </div>
        <div class="daily-change">
            {#if up_or_down}
                <img
                    class="daliy-change-svg"
                    src="./images/icon-up.svg"
                    alt="" />
                <p class="up">{flex_number} Today</p>
            {:else}
                <!-- else content here -->
                <img
                    class="daliy-change-svg"
                    src="./images/icon-down.svg"
                    alt="" />
                <p class="down">{flex_number} Today</p>
            {/if}

        </div>
    </div>
</div>
