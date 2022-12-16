<script lang="ts">
    import Slider from "./small/slider.svelte";
</script>
<div class="wrap review-wrap">
    <p class="slider-heading">
        Jak jste byli spokojení s našimi službami?
    </p>
    <Slider />
    <div class="review-inputs">
        <input type="text" placeholder="Jméno" />
        <input type="text" placeholder="Příjmení" />
        <textarea rows="10" placeholder="Prostor pro zpětnou vazbu" class="text-area"/>
        <button class="system-button">
            Odeslat folmulář
        </button>
    </div>
</div>

<style lang="scss" scoped>
    @import "../styles/vars.scss";
    .review-wrap {
        margin-bottom: 3rem;
        display: block;
        max-width: 100vw;
        .slider-heading{
            text-align: center;
            margin-bottom: 2rem;
        }
        .review-inputs {
            margin-top: 3rem;
            display: flex;
            flex-direction: column;
            gap: 0.5rem;
            input, textarea {
                background-color: $systemInputs;
                border-radius: 5px;
                padding: 0.5rem;
                color: #A7AFAE;
                resize: none;
                &:focus-visible{
                    // border: none;
                    outline: none;
                }
            }
            // {
                
            //     height: 10rem;
            // }
        }
    }
</style>
