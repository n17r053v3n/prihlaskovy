<script lang="ts">
    import { each } from "svelte/internal";
    import SystemButton from "../small/systemButton.svelte";
    export let ids: string = "form";
    export let inputs: string[] = [];
    export let textareas: string[] = [];
    export let pwds: string[] = [];
    export let buttonText: string = "Odeslat";
    export let link: string = "/send";
    export let checkboxes: string[] = [];
    export let type: string = "";
</script>

<div class="form-wrap">
    {#if type !== "outer"}
        {#each inputs as input, index}
            <input
                type="text"
                placeholder={input}
                class="text"
                id={ids + "-text-input-" + index}
            />
        {/each}
        {#each textareas as textarea, index}
            <textarea
                placeholder={textarea}
                class="text"
                id={ids + "-textarea-input-" + index}
                rows="5"
            />
        {/each}
        {#each pwds as pwd, index}
            <input
                type="password"
                placeholder={pwd}
                id={ids + "-pwd-input-" + index}
            />
        {/each}
    {:else}
        {#each inputs as input, index}
            <label class="text" for={ids + "-text-input-" + index}
                >{input}
                <input
                    type="text"
                    class="outer"
                    id={ids + "-text-input-" + index}
                />
            </label>
        {/each}
        {#each textareas as textarea, index}
            <label class="text" for={ids + "-textarea-input-" + index}
                >{textarea}
                <textarea
                    class="outer"
                    id={ids + "-textarea-input-" + index}
                    rows="5"
                />
            </label>
        {/each}
        {#each pwds as pwd, index}
            <label class="text" for={ids + "-textarea-input-" + index}
                >{pwd}
                <input
                    type="password"
                    class="outer"
                    id={ids + "-pwd-input-" + index}
                /></label
            >
        {/each}
    {/if}
    {#each checkboxes as checkbox, index}
        <label class="text check-label">
            <input
                type="checkbox"
                value={checkbox}
                class="text checkbox"
                id={ids + "-checkbox-input-" + index}
            />
            {checkbox}
        </label>
    {/each}
    <SystemButton {link} {buttonText} fullWidth={true} />
</div>

<style lang="scss" scoped>
    @import "../../styles/vars.scss";
    .form-wrap {
        // margin: 1rem 0;
        display: flex;
        flex-direction: column;
        gap: 0.5rem;
        align-items: center;
        justify-content: center;
        flex-wrap: wrap;
        :nth-child(n) {
            flex-shrink: 0;
        }
        width: 100%;
        input,
        textarea {
            background-color: $systemInputs;
            border-radius: 5px;
            padding: 0.5rem;
            // flex-shrink: 0;
            width: calc(100% - 1rem);
            // font-size: 0.75rem;
            // zoom: 0;
            transition: 0.1s ease;
            &::placeholder {
                color: #a7afae;
            }
            resize: none;
            &:focus-visible {
                outline: 2px solid $systemMedium;
                background-color: unset;
                // border: none;
            }
        }
        label {
            display: flex;
            flex-direction: column;
            // gap: 5rem;
            flex-wrap: wrap;
            width: 100%;
            input.checkbox {
                width: unset;
                // display: flex;
                // flex-direction: row;
                // flex-shrink: 1;
                // gap: 1rem;
            }
            input.outer,
            textarea.outer {
                border-radius: 70px;
                margin-top: 0.25rem;
                background-color: white;
                padding: 0.5rem 1.25rem;
                border: 2px solid $grey;
                width: calc(100% - 2.5rem - 4px);
            }
            // input.checkbox{
            //     width: 50px;
            // }
        }
        label.check-label{
            flex-direction: row;
            gap: 0.5rem;
            align-items: center;
            // justify-content: center;
        }
        :global(.system-button) {
            // width: (100% - );
            // flex-shrink: 1;
            margin-top: 0.5rem;
        }
        // {

        //     height: 10rem;
        // }
    }
    // label.text{
    //     padding-left: 1rem;
    // }
</style>
