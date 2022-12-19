<script lang="ts">
    import { slide } from "svelte/transition";
    import questions from "../../data/qna";
    let visibles: number[] = [];
    function visibility(inp: number) {
        console.log(inp);
        if (visibles.includes(inp)) {
            visibles = visibles.filter((e) => e !== inp);
        } else {
            visibles.push(inp);
        }
        console.log(visibles);
        visibles = visibles;
    }
</script>

<div class="wrap qna-wrap">
    <h6 class="section-heading">Časté otázky</h6>
    {#each questions as question, index}
        <!-- svelte-ignore a11y-click-events-have-key-events -->
        <div class="single-qna" on:click={() => visibility(index)}>
            <div class="single-qna-base">
                <p class="text">{question.question}</p>
                <img
                    src="/img/arrow.svg"
                    class={visibles.includes(index) ? "rotate" : ""}
                    alt=""
                />
            </div>
            {#if visibles.includes(index)}
                <div
                    class="text-small"
                    in:slide={{ duration: 200 }}
                    out:slide={{ duration: 200 }}
                >
                    {question.answer}
                </div>
            {/if}
        </div>
    {/each}
    <!-- <div class="space" /> -->
</div>

<style lang="scss" scoped>
    @import "../../styles/vars.scss";
    // .space {
    //     height: 1000px;
    // }
    .qna-wrap {
        display: flex;
        flex-direction: column;
        gap: 1rem;
        
    }
    .single-qna {
        display: flex;
        // justify-content: space-between;
        // align-items: center;
        flex-direction: column;
        padding: 0.75rem 2rem;
        border-radius: 33px;
        box-shadow: 2px 5px 20px #a8acab;
        user-select: none;
        .single-qna-base {
            display: flex;
            flex-direction: row;
            justify-content: space-between;
            align-items: center;
            width: 100%;
            flex-shrink: 0;
            .text {
                color: $systemLight;
                // font-size: 0.75rem;
                margin: 0;
            }
            img {
                transition: 0.25s ease;
            }
        }
        .text-small {
            margin: 1rem 0;
        }
    }
    .rotate {
        rotate: 90deg;
    }
    @media only screen and (min-width: 1536px){
        .qna-wrap{
            gap: 2rem;
        }
        .single-qna{
            padding: 2rem 3rem;
            .single-qna-base{

                img{
                    width: 50px;
                }
            }
        }
    }
</style>
