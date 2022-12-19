<script lang="ts">
    import SystemButton from "./systemButton.svelte";

    export let name: string;
    export let img: string;
    export let price: number;
    export let bullets: string[];
</script>

<div class="price-tag-wrap">
    <div class="price-tag-banner">
        <p class="text-small">{name}</p>
    </div>
    <img src="/img/price-tags/{img}.svg" class="thumbnail" alt={img} />
    <p class="text-large">{price}Kč</p>
    <p class="text-small">měsíčně</p>
    <p class="text-small dph">*Cena je uvedena bez DPH</p>
    <div class="price-tag-bullets">
        {#each bullets as bullet}
            <div class="price-tag-bullet">
                <p class="text-small">{bullet}</p>
            </div>
        {/each}
        <!-- <button class="system-button">MÁM ZÁJEM</button> -->
    </div>
    <SystemButton link="#" buttonText="MÁM ZÁJEM" size="small" />
</div>

<style lang="scss" scoped>
    @import "../../styles/vars.scss";
    .price-tag-wrap {
        border-radius: 33px;
        box-shadow: 2px 5px 60px #a8acab;
        display: flex;
        flex-direction: column;
        align-items: center;
        padding: 0 2rem 1rem;
        z-index: 2;
        background-color: white;
        overflow-x: hidden;
        & > .thumbnail {
            height: 3.5rem;
        }
        .text-large {
            color: $systemDark;
            font-weight: 700;
        }
    }

    .price-tag-banner {
        background-color: $systemDark;
        width: min-content;
        padding: 0.25rem 1.5rem 0.75rem;
        border-radius: 0 30px 30px 0;
        rotate: 90deg;
        align-self: flex-start;
        justify-self: flex-start;
        position: relative;
        top: 18px;
        right: 45px;
        .text-small {
            color: white;
            text-transform: uppercase;
        }
    }
    .price-tag-bullets {
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 0.5rem;
        width: 100%;
        margin: 1rem 0;
        // padding: 0 1rem;
    }
    .text-small {
        text-align: center;
    }
    .dph {
        font-size: 0.25rem;
    }
    .price-tag-bullet {
        border-bottom: 3px dashed $systemDarkest;
        // width: 70%;
        padding: 0.25rem;
    }

    @media only screen and (min-width: 1024px) {
    }

    @media only screen and (min-width: 1536px) {
        .price-tag-wrap {
            padding: 0 2rem 1rem;
            & > .thumbnail {
                height: 7rem;
                width: 7rem;
                z-index: 5;
            }
        }
        .price-tag-banner {
            padding: 0.5rem 1.5rem 0.75rem;
            top: 35px;
            right: 50px;
        }
        .dph {
            font-size: 0.75rem;
        }
    }
</style>
