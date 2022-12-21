<script>
    import ModalMenu from "../modalMenu.svelte";
    import SystemButton from "../small/systemButton.svelte";
    let active = false;
</script>

<div class="wrap nav-wrap">
    <div class="nav-img">
        <img src="/img/sys/logo-dark.png" alt="Logo" />
    </div>
    <div class="nav-menu nav-menu-desktop">
        <a href="#proc-my" class="nav-menu-item text-small">Proč my</a>
        <a href="#o-systemu" class="nav-menu-item text-small">O systému</a>
        <a href="#cenik" class="nav-menu-item text-small">Ceník</a>
        <a href="#kontakt" class="nav-menu-item text-small">Kontakt</a>
    </div>
    <SystemButton
        buttonText="Přihlášení pro členy"
        size="small"
        style="outlined"
    />
    <div class="nav-menu nav-menu-mobile">
        <button
            class="hamburger hamburger--boring {active ? 'is-active' : ''}"
            type="button"
            on:click={() => (active = !active)}
        >
            <span class="hamburger-box">
                <span class="hamburger-inner" />
            </span>
        </button>
    </div>
</div>
{#if active}
    <ModalMenu on:closeMenu={() => (active = !active)} />
{/if}

<style lang="scss" scoped>
    @import "../../styles/hamburgers.css";
    @import "../../styles/vars.scss";
    .nav-wrap {
        margin: 0;
        align-items: center;
        // flex-shrink: 0;
        // width: max-content;
        width: calc(100% - $padding * 2);
        justify-content: space-between;
        // padding: 1rem $padding;
        height: 100px;
        flex-direction: row;
        position: fixed;
        z-index: 999;
        background-color: white;
        :global(.system-button) {
            display: none;
        }
    }
    .nav-img {
        img {
            max-width: 7rem;
        }
    }
    // .nav-menu {
    // }
    .nav-menu-desktop {
        a {
            color: $grey;
        }
        display: none;
    }

    .nav-menu-mobile {
        .hamburger-box {
            width: 20px;
        }
        .hamburger-inner,
        .hamburger-inner::before,
        .hamburger-inner::after {
            background-color: $systemLight;
            width: 20px;
        }
        .is-active {
            .hamburger-inner,
            .hamburger-inner::before,
            .hamburger-inner::after {
                background-color: $systemLight;
                // width: 20px;
            }
        }
    }
    @media only screen and (min-width: 768px) {
        .nav-wrap {
            width: calc(100% - $padding-768 * 2);
        }
    }
    @media only screen and (min-width: 1024px) {
        .nav-wrap {
            width: calc(100% - $padding-1024 * 2);
            :global(.system-button) {
                display: block;
            }
        }
        .nav-menu-desktop {
            justify-self: center;
            display: flex;
            flex-direction: row;
            gap: 1rem;
            .nav-menu-item {
                font-weight: 500;
                &:hover {
                    scale: 1.1;
                    color: $systemMedium;
                }
            }
        }
        .nav-menu-mobile {
            display: none;
        }
    }
    @media only screen and (min-width: 1536px) {
        .nav-wrap {
            width: calc(100% - $padding-1536 * 2);
        }
    }
</style>
