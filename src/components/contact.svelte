<div class="wrap contact-wrap">
    <h4 class="text-large">Kontakt</h4>
    <p class="text">Tomáš Otruba</p>
    <p class="text">IČ: 704 62 810</p>
    <div class="contacts">
        <a href="mailto:info@prihlaskovysystem.cz"
            ><img
                src="/img/contact/mail.svg"
                alt=""
            />info@prihlaskovysystem.cz</a
        >
        <a href="tel:+420 775 069 225"
            ><img src="/img/contact/phone.svg" alt="" />+420 775 069 225</a
        >
    </div>
</div>

<style lang="scss" scoped>
    @import "../styles/vars.scss";
    .contact-wrap {
        margin-bottom: 3rem;
        .text-large {
            text-align: center;
            color: $systemLight;
            margin-bottom: 1rem;
        }
        .text {
            text-align: center;
        }
        .contacts{
            margin-top: 1rem;
            display: flex;
            flex-direction: column;
            gap: 0.5rem;
        }
        a {
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 0.5rem;
            color: $systemLight;
            img {
                height: 1rem;
            }
        }
    }
</style>
