<script lang="ts">
    import Slider from "./small/slider.svelte";
    import Form from "./basic/form.svelte";
</script>

<div class="wrap review-wrap">
    <p class="section-heading">Jak jste byli spokojení s našimi službami?</p>
    <Slider />
    <div class="review-inputs">
        <Form
            inputs={["Jméno", "Příjmení"]}
            textareas={["Prostor pro zpětnou vazbu"]}
        />
    </div>
</div>

<style lang="scss" scoped>
    @import "../styles/vars.scss";
    .review-wrap {
        display: block;
        max-width: 100vw;
        .review-inputs {
            margin-top: 1.5rem;
        }
        .section-heading {
            text-align: center;
            margin-bottom: 2rem;
        }
    }
    @media only screen and (min-width: 768px) {
        .review-wrap {
            .review-inputs {
                :global(.form-wrap){
                    flex-direction: row;
                }
                :global(input) {
                    width: calc(50% - 1.25rem);
                    flex-shrink: 1;
                }
            }
        }
    }
    @media only screen and (min-width: 1536px) {
        .review-wrap {
            .review-inputs {
                :global(input),
                :global(textarea) {
                    font-size: 1.25rem;
                }
            }
        }
    }
</style>
