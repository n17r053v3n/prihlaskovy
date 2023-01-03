<script lang="ts">
    export let buttonText: string = "Přihlásit se";
    export let link: string = "";
    export let size: string = "medium";
    export let style: string = "";
    export let fullWidth: boolean = false;
</script>

<a href={link} class="system-button {size} {style} {fullWidth ? "full-width" : ""}">
    {buttonText}
</a>

<style lang="scss" scoped>
    @import "../../styles/vars.scss";
    .system-button {
        background-color: $systemMedium;
        border-radius: 30px;
        border: none;
        color: #fff;
        transition: 0.25s ease;
        text-align: center;
        flex-shrink: 1;
        &:hover {
            cursor: pointer;
            scale: 1.1;
        }
    }
    .full-width:hover{
        scale: 1.025;
    }
    .outlined {
        background-color: #fff;
        border: 2px solid $systemMedium;
        color: $systemMedium;
    }
    .small {
        font-size: 0.75rem;
        padding: 0.25rem 1.25rem;
        &.full-width {
            width: calc(100% - 2.5rem);
        }
    }
    .medium {
        font-size: 1rem;
        padding: 0.5rem 3rem;
        &.full-width {
            width: calc(100% - 6rem);
        }
    }
    @media only screen and (min-width: 1024px) {
        .small {
            font-size: 1rem;
            padding: 0.4rem 2.75rem;
            &.full-width {
                width: calc(100% - 5.5rem);
            }
        }
        .medium {
            font-size: 1.25rem;
            padding: 0.6rem 5rem;
            &.full-width {
                width: calc(100% - 10rem);
            }
        }
    }
    @media only screen and (min-width: 1536px) {
        .small {
            font-size: 1.25rem;
            padding: 0.5rem 3rem;
            &.full-width {
                width: calc(100% - 6rem);
            }
        }
        .medium {
            font-size: 1.75rem;
            padding: 0.75rem 6rem;
            &.full-width {
                width: calc(100% - 12rem);
            }
        }
    }
</style>
