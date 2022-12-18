<div class="wrap partners-wrap">
    <p class="partners-p">Spolupracujeme</p>
    <div class="partners-images">
        <a href="https://aimsport.cz/sportovni-kemp/">
            <img src="/img/partners/aim.png" alt="aim" />
        </a>
        <a href="https://peacheskemp.cz/">
            <img src="/img/partners/peaches.png" alt="peaches" />
        </a>
    </div>
</div>

<style lang="scss" scoped>
    @import "../../styles/vars.scss";
    .partners-wrap {
        margin: 5rem 0;
        flex-direction: column;
        z-index: 1;
        .partners-p {
            font-size: 1.25rem;
            color: $systemLight;
            // font-weight: 400;
            text-align: center;
            width: 100%;
            flex-shrink: 0;
        }
        .partners-images {
            display: flex;
            flex-direction: row;
            align-items: center;
            width: 100%;
            gap: 2rem;
            a {
                flex-shrink: 1;
                width: 50%;
                z-index: 2;
                -webkit-filter: grayscale(1);
                filter: grayscale(1);
                transition: 0.5s ease;
                pointer-events: unset;
                &:hover {
                    -webkit-filter: grayscale(0);
                    filter: none;
                    scale: 1.2;
                }
                img{
                    width: 100%;
                }
            }
        }
    }
</style>
