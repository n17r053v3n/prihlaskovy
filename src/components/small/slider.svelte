<script lang="ts">
    let sliderValue = 5;
</script>

<div class="slider-wrap">
    <div class="slider-numbers">
        {#each { length: 11 } as _, index}
            <!-- svelte-ignore a11y-click-events-have-key-events -->
            <p on:click={() => (sliderValue = index)} class="slider-number text {sliderValue == index ? "active" : ""}">
                {index}
            </p>
        {/each}
    </div>
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
        <p class="text-small">
            Nebyli jsme spokojení
        </p>
        <p class="text-small">
            Největší spokojenost
        </p>
    </div>
</div>

<style lang="scss" scoped>
    @import "../../styles/vars.scss";
    .slider-wrap {
        display: flex;
        align-items: center;
        justify-content: center;
        flex-wrap: wrap;

        .slider-numbers {
            display: flex;
            flex-direction: row;
            width: 100%;
            // width: calc(100% - 5px);
            // flex-shrink: 0;
            // justify-content: space-between;
            // padding: 0 5px;
            .slider-number {
                display: flex;
                justify-content: center;
                // width: calc(100% / 10);
                width: 100%;
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
            width: calc(100% - ((100% / 11)) + 20px);
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
        // .sliderValue span.show {
        //     transform: translateX(-70%) scale(1);
        // }
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
        // .field .value {
        //     position: absolute;
        //     font-size: 18px;
        //     color: $systemLight;
        //     font-weight: 600;
        // }
        // .field .value.left {
        //     left: -22px;
        // }
        // .field .value.right {
        //     right: -43px;
        // }
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
            .text-small{
                color: $systemLight;
            }
        }
    }
</style>
