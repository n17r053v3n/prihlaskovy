<script lang="ts">
    export let bigText: string;
    export let smallText: string;
    export let img: string;
    // export let imgMarginTop: string = "0"; // in rems
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
        style="margin-right: {parseInt(
            imgMarginRight
        )}rem;"
    />
</div>

<style lang="scss" scoped>
    @import "../../styles/vars.scss";

    .review-cta {
        // scroll-margin-top: 6.25rem;
        margin: 5rem 0 3rem;
        padding-top: 3rem;
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
            margin-left: $padding;
        }
        .text-big {
            max-width: 245px;
            text-transform: uppercase;
        }
        .text-small {
            max-width: 200px;
            margin-top: 0.5rem;
            font-weight: 500;
        }
        img {
            align-self: flex-end;
            margin-right: -8.5rem;
            // width: 60%;
        }
    }
    @media only screen and (min-width: 768px) {
        .review-cta {
            background-size: 500px;
            padding-top: 6rem;
            background-position: -100px 0;
            p {
                margin-left: $padding-768;
            }
            .text-big {
                max-width: 300px;
            }
            .text-small {
                max-width: 250px;
                margin-top: 1rem;
            }
            img {
                margin-top: -6rem;
                // width: 800px;
                height: 300px;
            }
        }
    }
    @media only screen and (min-width: 1024px) {
        .review-cta {
            background-size: 600px;
            padding-top: 7rem;
            background-position: -100px 0;
            p {
                margin-left: $padding-1024;
            }
            .text-big {
                max-width: 400px;
            }
            .text-small {
                max-width: 300px;
                margin-top: 1rem;
            }
            img {
                margin-top: -10rem;
                // width: 800px;
                height: 400px;
            }
        }
    }
    @media only screen and (min-width: 1536px) {
        .review-cta {
            background-size: 900px;
            padding-top: 10rem;
            p {
                margin-left: $padding-1536;
            }
            .text-big {
                max-width: 600px;
            }
            .text-small {
                max-width: 500px;
            }
            img {
                margin-top: -10rem;
                // width: 800px;
                height: 500px;
            }
        }
    }
</style>
