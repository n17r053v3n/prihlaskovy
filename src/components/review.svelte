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
            align-items: center;

            input, textarea {
                background-color: $systemInputs;
                border-radius: 5px;
                padding: 0.5rem;
                // flex-shrink: 0;
                width: 100%;
                // font-size: 0.75rem;
                // zoom: 0;
                transition: 0.1s ease;
                &::placeholder{
                    color: #A7AFAE;
                }
                resize: none;
                &:focus-visible{
                    outline: 2px solid $systemMedium;
                    background-color: unset;
                    // border: none;
                }
            }
            :global(.system-button){
                width: 60%;
                flex-shrink: 1;
                margin-top: 0.5rem;
            }
            // {
                
            //     height: 10rem;
            // }
        }
    }
    @media only screen and (min-width: 768px){
        .review-wrap {
            .review-inputs {
                flex-direction: row;
                justify-content: center;
                flex-wrap: wrap;
                input{
                    width: calc(50% - 1.25rem);
                }
            }

        }
    }
    @media only screen and (min-width: 1536px){
        .review-wrap {
            .review-inputs {
                input, textarea{
                    font-size: 1.25rem;
                }
            }

        }
    }
</style>
