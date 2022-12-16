<script lang="ts">
    export let buttonText: string = "Přihlásit se";
    export let link: string = "";
    export let size: string = "medium";
</script>

<a href={link} class="system-button {size}">
        {buttonText}
</a>

<style lang="scss" scoped>
    @import "../../styles/vars.scss";
    .system-button {
        background-color: $systemDark;
        border-radius: 30px;
        border: none;
        color: #fff;
        transition: 0.25s ease;
        text-align: center;
        &:hover {
            cursor: pointer;
            scale: 1.15;
        }
    }
    .small{
        font-size: 0.75rem;
        padding: 0.25rem 1.25rem;
    }
    .medium{
        font-size: 1rem;
        padding: 0.5rem 3rem;
    }
</style>
