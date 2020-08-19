<script>
    let themeMode = false;
    import Cards from "./Cards.svelte";
    import Details from "./Details.svelte";
    function handleThemeColor(){
        window.document.body.classList.toggle("dark");
        window.document.body.classList.toggle("light");
        themeMode = !themeMode;
    }
    
</script>

<style type="text/scss">
    .hr {
        width: 326px;
        margin: 0 auto;
        margin-bottom: 16px;
        color: #333a55;
    }
    .d-block {
        display: block;
    }
    .mb-normal {
        margin-bottom: 24px;
    }
    .dashboard-header {
        padding: 36px 25px 0 25px;
        h3 {
            color: var(--text-2);
            transition: background 500ms ease-in-out, color 1000ms ease-in-out;

        }
    }
    .overview {
        padding: 0 25px 0 25px;
    }
    .header {
        h3 {
            font-style: normal;
            font-weight: bold;
            font-size: 24px;
            line-height: 29px;
            color: var(--text-2);
            transition:color 1000ms ease-in-out;

        }
        p {
            font-style: normal;
            font-weight: bold;
            font-size: 14px;
            line-height: 17px;
            color: var(--text-1);
            transition: color 1000ms ease-in-out;

        }
    }
    .theme {
        display: flex;
        justify-content: space-between;
        margin-bottom: 40px;
        p {
            font-style: normal;
            font-weight: bold;
            font-size: 14px;
            line-height: 17px;
            color: var(--text-2);
            transition: color 1000ms ease-in-out;
        }
        &--btn {
            cursor: pointer;
            width: 48px;
            height: 24px;
            display: flex;
            justify-content: flex-start;
            align-items: center;
            background: linear-gradient(225deg, #40db82 0%, #388fe7 98.02%);
            border-radius: 12px;
            &__circle {
                background: #252b42;
                width: 18px;
                height: 18px;
                border-radius: 50%;
                margin: 0 4px;
            }
        }
    }
    .toggleDark{
        justify-content: flex-start !important;
    }
    .toggleLight{
        justify-content: flex-end !important;
        background: #F1F3FA !important;
    }
    .mb-27px {
        margin-bottom: 27px;
    }
    .details-container{
            padding: 0 24px;
        }
    @media (min-width: 1200px) {
        .dashboard-header {
            padding: 36px 165px 0px 165px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            width: 1110px;
            .theme {
                display: flex;
                justify-content: flex-end;
                align-items: center;
                p {
                    margin-right: 13px;
                }
            }
        }
        .cards-container {
            padding: 0 165px 0px 165px;
            margin-bottom: 46px;
        }
        .details-container {
            padding: 0 165px 0px 165px;
        }
        .d-xxl-none {
            display: none;
        }
        .mb-large {
            margin-bottom: 46px;
        }
        .overview {
            padding: 0 165px 0px 165px;
        }
    }
</style>

<main>
    <div class="dashboard-header">
        <div class="header mb-normal mb-large">
            <h3>Social Media Dashboard</h3>
            <p class="subheader">Total Followers: 23,004</p>
        </div>
        <hr class="hr d-block d-xxl-none" />
        <div class="theme">
            {#if themeMode === 'light'}
                <p class="theme--text">Dark Mode</p>
            {:else}
                <p class="theme--text">Light Mode</p>
            {/if}
            <div on:click={handleThemeColor} class={themeMode == false?"toggleDark theme--btn":"toggleLight theme--btn"}>
                <div class="theme--btn__circle" />
            </div>
        </div>
    </div>
    <div class="cards-container">
        <Cards />
    </div>
    <div class="overview mb-normal">
        <div class="header">
            <h3 class="">Overview - Today</h3>
        </div>
    </div>
    <div class="details-container">
        <Details />
    </div>
</main>
