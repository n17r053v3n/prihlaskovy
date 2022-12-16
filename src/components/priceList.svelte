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
    <div class="price-list-tags">
        {#each priceTags as priceTag}
            <!-- <div class="price-list-tag"> -->
                <PriceTag
                    name={priceTag.name}
                    img={priceTag.img}
                    price={priceTag.price}
                    bullets={priceTag.bullets}
                />
            <!-- </div> -->
        {/each}
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
        :global(.price-tag-wrap) {
            //vnitrni komponenta
            width: 150px;
            flex-shrink: 0;
        }
    }
</style>
