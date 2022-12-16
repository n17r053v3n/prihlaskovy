<script lang="ts">
    export let bigText: string;
    export let smallText: string;
    export let img: string;
    export let imgMarginTop: string; // in rems
    export let imgMarginRight: string; // in rems
</script>

<div class="review-cta">
    <p class="review-cta-p">{bigText}</p>
    <p class="review-cta-p-small">
        {smallText}
    </p>
    <img src="/img/{img}.png" alt={img} style="margin-top: {parseInt(imgMarginTop)}rem; margin-right: {parseInt(imgMarginRight)}rem;"/>
</div>

<style lang="scss">
    @import "../../styles/vars.scss";

    .review-cta {
        margin: 5rem 0 3rem;
        display: flex;
        flex-direction: column;
        background-image: url("/img/text-background.svg");
        // background-size: 90%;
        background-size: 335px;
        background-position: -40px 0;
        background-repeat: no-repeat;
        // padding: 3.5rem 2rem;
        p {
            color: white;
            margin-left: 2rem;
            
        }
        .review-cta-p {
            font-size: 1.5rem;
            margin-top: 3.5rem;
            max-width: 240px;
        }
        .review-cta-p-small {
            font-size: 0.5rem;
            max-width: 200px;
        }
        img {
            align-self: flex-end;
            margin-right: -8.5rem;
            // width: 60%;
        }
    }
</style>
