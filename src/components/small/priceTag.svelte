<script lang="ts">
    import SystemButton from "./systemButton.svelte";

    export let name: string;
    export let img: string;
    export let price: number;
    export let bullets: string[];
</script>

<div class="background-wrap">
    <img src="/img/price-tags/background.svg" class="background" alt="" />
    <div class="price-tag-wrap">
        <div class="price-tag-banner">
            <p class="price-tag-p">{name}</p>
        </div>
        <img src="/img/price-tags/{img}.svg" class="thumbnail" alt={img} />
        <p class="price-tag-price">{price}Kč</p>
        <p class="price-tag-p">měsíčně</p>
        <p class="price-tag-p-small">*Cena je uvedena bez DPH</p>
        <div class="price-tag-bullets">
            {#each bullets as bullet}
                <div class="price-tag-bullet">
                    <p class="price-tag-p">{bullet}</p>
                </div>
            {/each}
            <!-- <button class="system-button">MÁM ZÁJEM</button> -->
            <SystemButton link="#" buttonText="MÁM ZÁJEM" size="small"/>
        </div>
    </div>
</div>

<style lang="scss" scoped>
    @import "../../styles/vars.scss";
    .price-tag-wrap {
        border-radius: 33px;
        box-shadow: 2px 5px 60px #a8acab;
        display: flex;
        flex-direction: column;
        align-items: center;
        padding-bottom: 1rem;
        z-index: 2;
        background-color: white;
        overflow-x: hidden;
        & > .thumbnail {
            width: 3.5rem;
        }
        .price-tag-price {
            color: $systemDark;
            font-size: 1.75rem;
            font-weight: 700;
        }
    }
    .background-wrap{
        display: flex;
        justify-content: center;
        align-items: center;
        // max-width: 100vw;
        // background-image: url("/img/price-tags/background.svg");
    }
    .background {
        position: absolute;
        // margin-top: 5rem;
        z-index: -1;
        // padding-left: 10rem;
        width: 100%;
        flex-grow: 0;
        // scale: 1.75;
        overflow-x: hidden;
        // object-position: 90%;
        // object-fit: contain;
    }
    .price-tag-banner {
        background-color: $systemDark;
        width: min-content;
        padding: 0.25rem 1.5rem 0.75rem 0.5rem;
        border-radius: 0 30px 30px 0;
        rotate: 90deg;
        align-self: flex-start;
        justify-self: flex-start;
        position: relative;
        top: 20px;
        right: 5px;
        .price-tag-p {
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
        margin-top: 1rem;
    }
    .price-tag-p {
        font-size: 0.5rem;
        text-align: center;
    }
    .price-tag-p-small {
        font-size: 0.25rem;
        text-align: center;
    }
    .price-tag-bullet {
        border-bottom: 3px dashed $systemDarkest;
        width: 70%;
        padding-bottom: 0.25rem;
    }
</style>
