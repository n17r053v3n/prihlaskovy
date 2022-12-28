<script lang="ts">
    import SystemButton from "./small/systemButton.svelte";
</script>

<div class="wrap landing-wrap page-land">
    <div class="landing-left">
        <h4 class="text-super-large">
            <span>Všechno na</span><br>jednom místě
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
        // padding-top: 3rem;
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


    @media only screen and (min-width: 768px){
        .landing-wrap{
            // padding-top: 5rem;
            flex-direction: row;
            .landing-left, .landing-right{
                width: 50%;
            }
            .landing-right{
                margin-top: -1rem;
            }
        }
    }
    @media only screen and (min-width: 1024px){
        .landing-wrap{
            // padding-top: 6rem;
            .landing-right{
                margin-top: -2rem;
            }
        }
    }
</style>
