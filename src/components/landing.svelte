<script lang="ts">
    import SystemButton from "./small/systemButton.svelte";
</script>

<div class="wrap landing-wrap">
    <div class="landing-left">
        <h4 class="text-super-large">
            <span>Všechno na</span> jednom místě
        </h4>
        <p class="text">
            Hledáte správny systém pro Vás? Jste tu správně.
        </p>
        <SystemButton link="/login"/>
    </div>
    <div class="landing-right">
        <img src="/img/landing.svg" alt="">
    </div>
</div>

<style lang="scss" scoped>
    @import "../styles/vars.scss";
    .landing-wrap{
        // margin-top: 2.5rem;
        flex-direction: column;
        gap: 3rem;
        padding-top: 8.75rem;
    }
    .landing-left{
        display: flex;
        flex-direction: column;
        gap: 1rem;
        align-items: flex-start;
        // > .system-button{
        //     flex-grow: 0;
        // }
    }
    .text-super-large {
        // font-size: 2.25rem;
        span {
            color: $systemLight;
        }
    }
    .landing-right{
        &> img{
            width: 100%;
        }
    }



    @media only screen and (min-width: 1024px){
        .landing-wrap{
            flex-direction: row;
            .landing-left, .landing-right{
                width: 50%;
            }
        }
    }
</style>
