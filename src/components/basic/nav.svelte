<script>
    import navItems from "../../data/nav-items";
</script>

<div class="nav-menu">
    {#each navItems as navItem}
    <a href={navItem.link} class="nav-menu-item text-small">{navItem.title}</a>
    {/each}
</div>

<style lang="scss">
    @import "../../styles/vars.scss";
    .nav-menu {
        display: flex;
        flex-direction: column;
        // flex-direction: row;
        gap: 0.5rem;
    }
    .nav-menu-item {
        text-align: center;
        color: white;
        transition: 0.25s ease;
        font-weight: 500;

        &:hover {
            scale: 1.1;
            color: $systemMedium;
        }
    }
    // .nav-menu {
    // }
    .vertical {
        flex-direction: column;
    }
    @media only screen and (min-width: 768px){
        .nav-menu{
            flex-direction: row;
            gap: 1rem;
        }
    }
    // @media only screen and (min-width: 1024px) {
    //     .nav-menu-item {
    //         font-weight: 500;
    //         &:hover {
    //             scale: 1.1;
    //             color: $systemMedium;
    //         }
    //     }
    // }
</style>
