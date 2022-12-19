<script lang="ts">
    export let bigText: string;
    export let smallText: string;
    export let img: string;
    export let imgMarginTop: string = "0"; // in rems
    export let imgMarginRight: string = "0"; // in rems
    export let id: string = "";
</script>

<!-- <div  /> -->
<div class="review-cta" {id}>
    <p class="text-big">{bigText}</p>
    <p class="text-small">
        {smallText}
    </p>
    <img
        src="/img/{img}.png"
        alt={img}
        style="margin-top: {parseInt(imgMarginTop)}rem; margin-right: {parseInt(
            imgMarginRight
        )}rem;"
    />
</div>

<style lang="scss" scoped>
    @import "../../styles/vars.scss";

    .review-cta {
        scroll-margin-top: 6.25rem;
        margin: 5rem 0 3rem;
        padding-top: 3.5rem;
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
        .text-big {
            max-width: 240px;
        }
        .text-small {
            max-width: 200px;
            margin-top: 0.5rem;
        }
        img {
            align-self: flex-end;
            margin-right: -8.5rem;
            // width: 60%;
        }
    }
</style>
