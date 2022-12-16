<script lang="ts">
    import Slider from "./small/slider.svelte";
    import SystemButton from "./small/systemButton.svelte";
</script>
<div class="wrap review-wrap">
    <p class="section-heading">
        Jak jste byli spokojení s našimi službami?
    </p>
    <Slider />
    <div class="review-inputs">
        <input type="text" placeholder="Jméno" />
        <input type="text" placeholder="Příjmení" />
        <textarea rows="5" placeholder="Prostor pro zpětnou vazbu" class="text-area"/>
        <SystemButton link="/send" buttonText="Odeslat folmulář"/>
    </div>
</div>

<style lang="scss" scoped>
    @import "../styles/vars.scss";
    .review-wrap {
        margin-bottom: 3rem;
        display: block;
        max-width: 100vw;
        .section-heading{
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
                &::placeholder{
                    color: #A7AFAE;
                }
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
