<footer class="wrap footer-wrap">
    <img src="/img/sys/logo-white.png" alt="logo" />
    <p class="section-heading">Všechno na jednom místě</p>
    <div class="nav-menu nav-menu-desktop">
        <a href="#proc-my" class="nav-menu-item text-small">Proč my</a>
        <a href="#o-systemu" class="nav-menu-item text-small">O systému</a>
        <a href="#cenik" class="nav-menu-item text-small">Ceník</a>
        <a href="#kontakt" class="nav-menu-item text-small">Kontakt</a>
    </div>
    <div class="socials">
        <a href="facebook">
            <img src="/img/contact/facebook.svg" alt="facebook" />
        </a>
        <a href="instagram">
            <img src="/img/contact/instagram.svg" alt="instagram" />
        </a>

        <a href="twitter">
            <img src="/img/contact/twitter.svg" alt="twitter" />
        </a>
    </div>
    <p class="text-small">© Designed by Antónia Kenderešová | TK Design</p>
</footer>

<style lang="scss" scoped>
    @import "../../styles/vars.scss";
    .footer-wrap {
        margin: 0;
        padding: 2rem $padding;

        background-color: $systemLight;
        flex-direction: column;
        align-items: center;
        gap: 0.5rem;
        .section-heading {
            text-align: center;
        }
        & > img {
            max-width: 7rem;
            margin-bottom: 1rem;
        }
        .nav-menu {
            // margin-top: 1rem;
        }
        .socials {
            // margin-top: 1rem;
            display: flex;
            gap: 1rem;
            img {
                width: 25px;
                transition: 0.25s ease;
                pointer-events: unset;
                &:hover {
                    scale: 1.25;
                }
            }
        }
        .text-small {
            // margin-top: 0.5rem;
            color: white;
        }
    }
    @media only screen and (min-width: 1024px) {
        .footer-wrap {
            gap: 0.75rem;
            padding: 4rem $padding-1024;
            & > img {
                max-width: 10rem;
            }
            .socials {
                gap: 1.5rem;
                img {
                    width: 30px;
                }
            }
        }
    }
    @media only screen and (min-width: 1536px) {
        .footer-wrap {
            gap: 1rem;
            .socials {
                gap: 2rem;
                img {
                    width: 35px;
                }
            }
        }
    }
</style>
