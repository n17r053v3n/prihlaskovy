<script lang="ts">
    import { onMount } from "svelte";
    let sliderValue = 0;
    // not important
    // onMount(() => {
    //     const slideValue = document.getElementById("span");
    //     const inputSlider = document.getElementById("input");
    //     if (inputSlider != null && slideValue != null) {
    //         inputSlider.oninput = () => {
    //             let value = (<HTMLInputElement>inputSlider).value;
    //             slideValue.textContent = value;
    //             slideValue.style.left = parseInt(value) / 2 + "%";
    //             slideValue.classList.add("show");
    //             console.log(value);
    //         };
    //         inputSlider.onblur = () => {
    //             slideValue.classList.remove("show");
    //         };
    //     }
    // });
    // $: console.log(sliderValue)
</script>

<div class="slider-wrap">
    <div class="slider-numbers">
        <!-- classic foreach to generate numbers (important) -->
        {#each { length: 11 } as _, index}
            <!-- svelte-ignore a11y-click-events-have-key-events -->
            <p on:click={() => (sliderValue = index)} class="slider-number {sliderValue == index ? "active" : ""}">
                {index}
            </p>
        {/each}

        <!-- <p class="slider-number">
            1
        </p>
        <p class="slider-number">
            2
        </p>
        <p class="slider-number">
            3
        </p>
        <p class="slider-number">
            4
        </p>
        <p class="slider-number">
            5
        </p>
        <p class="slider-number">
            6
        </p>
        <p class="slider-number">
            7
        </p>
        <p class="slider-number">
            8
        </p>
        <p class="slider-number">
            9
        </p>
        <p class="slider-number">
            10
        </p> -->
    </div>
    <!-- important -->
    <div class="range">
        <div class="sliderValue">
            <span id="span">100</span>
        </div>
        <div class="field">
            <input
                type="range"
                min="0"
                max="10"
                bind:value={sliderValue}
                step="1"
                id="input"
            />
        </div>
    </div>
    <div class="range-descriptions">
        <p class="range-description">
            Nebyli jsme spokojení
        </p>
        <p class="range-description">
            Největší spokojenost
        </p>
    </div>
</div>

<style lang="scss">
    @import "../../styles/vars.scss";
    // $systemLight: #02CBC6;
    .slider-wrap {
        display: flex;
        align-items: center;
        justify-content: center;
        flex-wrap: wrap;

        // important
        .slider-numbers {
            display: flex;
            flex-direction: row;
            // width: 100%;
            width: calc(100% - 5px);
            // flex-shrink: 0;
            // justify-content: space-between;
            // padding: 0 5px;
            .slider-number {
                display: flex;
                justify-content: center;
                // width: calc(100% / 10);
                width: 100%;
                font-size: 1rem;
                transition: 0.25s ease;
                color: $systemLight;
                &:hover {
                    scale: 1.5;
                    color: $systemDark;
                    cursor: pointer;
                }
            }
            .active {
                scale: 1.5;
                color: $systemDark;
            }
        }

        // important
        .range {
            width: calc(100% - 10px);
            // height: 80px;
            // padding: 0 5px;z
            margin-top: 1rem;
            // width: 100%;
            background: #fff;
            border-radius: 10px;
            // box-shadow: 2px 4px 8px rgba(0, 0, 0, 0.1);
            flex-shrink: 1;
        }
        // not important
        .sliderValue {
            position: relative;
            width: 100%;
            height: 3px;
        }
        .sliderValue span {
            position: absolute;
            height: 45px;
            width: 45px;
            transform: translateX(-70%) scale(0);
            font-weight: 500;
            top: -40px;
            line-height: 55px;
            z-index: 2;
            color: #fff;
            transform-origin: bottom;
            transition: transform 0.3s ease-in-out;
        }
        .sliderValue span.show {
            transform: translateX(-70%) scale(1);
        }
        .sliderValue span:after {
            position: absolute;
            content: "";
            height: 100%;
            width: 100%;
            background: $systemLight;
            border: 3px solid #fff;
            z-index: -1;
            left: 50%;
            transform: translateX(-50%) rotate(45deg);
            border-bottom-left-radius: 50%;
            box-shadow: 0px 0px 8px rgba(0, 0, 0, 0.1);
            border-top-left-radius: 50%;
            border-top-right-radius: 50%;
        }
        .field {
            display: flex;
            align-items: center;
            justify-content: center;
            height: 100%;
            position: relative;
        }
        .field .value {
            position: absolute;
            font-size: 18px;
            color: $systemLight;
            font-weight: 600;
        }
        .field .value.left {
            left: -22px;
        }
        .field .value.right {
            right: -43px;
        }
        .range input {
            -webkit-appearance: none;
            width: 100%;
            height: 5px;
            // height: 3px;
            background: $systemInputs;
            border-radius: 5px;
            outline: none;
            border: none;
            z-index: 20;
            // transition: 0.25s ease;
            // touch-action: cross-slide-x;
            &:hover{
                cursor: pointer;
            }
        }
        .range input::-webkit-slider-thumb {
            -webkit-appearance: none;
            width: 20px;
            height: 20px;
            background: red;
            border-radius: 50%;
            background: $systemLight;
            border: 1px solid $systemLight;
            cursor: pointer;
        }
        .range input::-moz-range-thumb {
            -webkit-appearance: none;
            width: 20px;
            height: 20px;
            background: red;
            border-radius: 50%;
            background: $systemLight;
            border: 1px solid $systemLight;
            cursor: pointer;
        }
        .range input::-moz-range-progress {
            background: $systemLight; //this progress background is only shown on Firefox
        }
        .range-descriptions{
            margin-top: 1rem;
            display: flex;
            justify-content: space-between;
            width: 100%;
            padding: 0 0.5rem;
            .range-description{
                font-size: 0.5rem;
                color: $systemLight;
            }
        }
    }
</style>
