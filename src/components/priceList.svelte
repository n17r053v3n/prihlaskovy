<script>
    import priceTags from "../data/price-tags";
    import PriceTag from "./small/priceTag.svelte";
</script>

<div class="wrap price-list-wrap" id="cenik">
    <div class="price-list-top">
        <p class="price-list-p">Vyberte si plán vhodný pro Vaši firmu</p>
        <h4 class="price-list-h4">Ceník našich systémů</h4>
        <p class="price-list-p-small">
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
    .price-list-p {
        text-align: center;
        font-size: 1rem;
    }
    .price-list-h4 {
        text-align: center;
        font-size: 1.5rem;
        color: $systemLight;
    }
    .price-list-p-small {
        text-align: center;
        font-size: 0.5rem;
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
