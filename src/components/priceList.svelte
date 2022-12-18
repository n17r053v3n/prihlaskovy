<script>
    import priceTags from "../data/price-tags";
    import PriceTag from "./small/priceTag.svelte";
</script>

<div class="wrap price-list-wrap" id="cenik">
    <div class="price-list-top">
        <p class="text">Vyberte si plán vhodný pro Vaši firmu</p>
        <h4 class="text-big">Ceník našich systémů</h4>
        <p class="text-small">
            Cenové plány podle Vašich potřeb. Vyberte si ten správny pro Vás.
        </p>
    </div>
    <div class="price-tags-background-wrap">
        <img src="/img/price-tags/background.svg" class="background" alt="" />
        <div class="price-list-tags">
            {#each priceTags as priceTag}
                <div class="price-tag-background-wrap">
                    <img
                        src="/img/price-tags/background.svg"
                        class="background"
                        alt=""
                    />
                    <!-- <div class="price-list-tag"> -->
                    <PriceTag
                        name={priceTag.name}
                        img={priceTag.img}
                        price={priceTag.price}
                        bullets={priceTag.bullets}
                    />
                    <!-- </div> -->
                </div>
            {/each}
        </div>
    </div>
</div>

<style lang="scss" scoped>
    @import "../styles/vars.scss";
    #cenik {
        scroll-margin-top: 100px;
    }
    .price-list-top {
        display: flex;
        flex-direction: column;
        gap: 0.25rem;
    }
    .text {
        text-align: center;
    }
    .text-big {
        text-align: center;
        color: $systemLight;
    }
    .text-small {
        text-align: center;
    }
    .price-list-tags {
        //vnejsi komponenta
        display: flex;
        flex-direction: column;
        align-items: center;
        flex-shrink: 0;
        gap: 1.5rem;
        margin-top: 5rem;
        // .price-list-tag{
        //     background-image: url("/img/price-tags/background.svg");
        //     width: 100%;
        // }
        .price-tag-background-wrap {
            display: flex;
            justify-content: center;
            align-items: center;
            // max-width: 100vw;
            // background-image: url("/img/price-tags/background.svg");
        }
        :global(.price-tag-wrap) {
            //vnitrni komponenta
            // width: 50%;
            flex-shrink: 0;
        }
    }
    .price-tags-background-wrap {
        display: flex;
        justify-content: center;
        align-items: center;
        & > .background {
            display: none;
        }
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
    @media only screen and (min-width: 1024px) {
        .price-list-tags {
            flex-direction: row;
            gap: 3rem;
            .price-tag-background-wrap {
                .background {
                    display: none;
                }
            }
        }
        .price-tags-background-wrap {
            display: flex;
            justify-content: center;
            align-items: center;
            & > .background {
                display: block;
            }
        }
    }
</style>