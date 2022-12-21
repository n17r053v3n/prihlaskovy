<script>
    import { each } from "svelte/internal";
    import aboutSystem from "../data/about-system";
</script>

<div class="wrap system-wrap" id="o-systemu">
    {#each aboutSystem as data}
        <div class="system-single">
            <div class="system-single-top">
                <img src="/img/about-system/{data.img}.svg" alt={data.img} />
                <h6 class="section-heading">{data.name}</h6>
            </div>
            <p class="text">{data.preBold}<span>{data.bold}</span>{data.afterBold}</p>
        </div>
    {/each}
</div>

<style lang="scss" scoped>
    @import "../styles/vars.scss";
    // #o-systemu {
    //     scroll-margin-top: 100px;
    // }
    .system-wrap {
        gap: 3.25rem;
        margin: 6rem 0;
    }
    .system-single {
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 1rem;
        .system-single-top {
            display: flex;
            flex-direction: column;
            align-items: center;
            width: 100%;
            // justify-content: center;
            gap: 1rem;
            & > img {
                width: 2.75rem;
            }
            .section-heading {
                text-align: center;
                color: $systemLight;
                width: 50%;
            }
        }
        .text {
            text-align: center;
            & > span {
                font-weight: bold;
            }
        }
    }
    @media only screen and (min-width: 768px) {
        .system-wrap {
            flex-direction: row;
            .system-single {
                width: calc(100% / 3);
                // gap: unset;
                .system-single-top {
                    // margin-top: auto;
                    justify-content: space-between;
                    .section-heading {
                        width: 100%;
                    }
                }
                // .text{
                //     // margin-top: auto;
                //     // margin-bottom: auto;
                //     // justify-self: baseline
                // }
            }
        }
    }
</style>
