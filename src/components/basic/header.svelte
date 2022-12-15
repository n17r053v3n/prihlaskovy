<script>
    import ModalMenu from "../modalMenu.svelte";
    let active = false;
</script>

<div class="wrap nav-wrap">
    <div class="nav-img">
        <img src="/img/sys/logo-dark.png" alt="Logo" />
    </div>
    <div class="nav-menu nav-menu-desktop">
        <a href="#proc-my" class="nav-menu-item">Proč my</a>
        <a href="#o-systemu" class="nav-menu-item">O systému</a>
        <a href="#cenik" class="nav-menu-item">Ceník</a>
        <a href="#kontakt" class="nav-menu-item">Kontakt</a>
    </div>
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
    <ModalMenu on:closeMenu={() => active = !active}/>
{/if}

<style lang="scss">
    @import "../../styles/hamburgers.css";
    @import "../../styles/vars.scss";
    .nav-wrap {
        align-items: center;
        width: calc(100% - $padding * 2);
        justify-content: space-between;
        // padding: 1rem $padding;
        height: 100px;
        flex-direction: row;
        position: fixed;
		z-index: 999;
        background-color: white;
    }
    .nav-img {
        img {
            max-width: 7rem;
        }
    }
    // .nav-menu {
    // }
    .nav-menu-desktop {
        display: none;
    }
    .nav-menu-mobile {
        .hamburger-box{
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
</style>
