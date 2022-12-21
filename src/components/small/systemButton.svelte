<script lang="ts">
    export let buttonText: string = "Přihlásit se";
    export let link: string = "";
    export let size: string = "medium";
    export let style: string = ""
</script>

<a href={link} class="system-button {size} {style}">
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
        &:hover {
            cursor: pointer;
            scale: 1.1;
        }
    }
    .outlined{
        background-color: #fff;
        border: 2px solid $systemMedium;
        color: $systemMedium;
    }
    .small{
        font-size: 0.75rem;
        padding: 0.25rem 1.25rem;
    }
    .medium{
        font-size: 1rem;
        padding: 0.5rem 3rem;
    }
    @media only screen and (min-width: 1024px){
        .small{
            font-size: 1rem;
            padding: 0.4rem 2.75rem;
        }
        .medium{
            font-size: 1.25rem;
            padding: 0.6rem 5rem;
        }
    }
    @media only screen and (min-width: 1536px){
        .small{
            font-size: 1.25rem;
            padding: 0.5rem 3rem;
        }
        .medium{
            font-size: 1.75rem;
            padding: 0.75rem 6rem;
        }
    }
</style>
