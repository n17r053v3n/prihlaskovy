<script>
    import { each } from "svelte/internal";
    import aboutSystem from "../data/about-system";
</script>
<div class="wrap system-wrap" id="o-systemu">
    {#each aboutSystem as data}
    <div class="system-single">
        <img src="/img/about-system/{data[0]}.svg" alt="{data[0]}" />
        <h6 class="system-single-h6">{data[1]}</h6>
        <p class="system-single-p">{data[2]}<span>{data[3]}</span>{data[4]}</p>
    </div>
    {/each}
</div>


<style lang="scss">
    @import "../styles/vars.scss";
    #o-systemu{
        scroll-margin-top: 100px;
    }
    .system-wrap{
        gap: 3.25rem;
        margin: 4rem 0;
    }
    .system-single{
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 1rem;
        &> img{
            width: 2.75rem;
        }
        .system-single-h6{
            text-align: center;
            color: $systemLight;
            width: 50%;
        }
        .system-single-p{
            text-align: center;
            &> span{
                font-weight: bold;
            }
        }
    }
</style>