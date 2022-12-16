<div class="wrap contact-wrap">
    <h4 class="contact-h4">Kontakt</h4>
    <p class="contact-p">Tomáš Otruba</p>
    <p class="contact-p">IČ: 704 62 810</p>
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

<style lang="scss">
    @import "../styles/vars.scss";
    .contact-wrap {
        margin-bottom: 3rem;
        .contact-h4 {
            font-size: 1.5rem;
            text-align: center;
            color: $systemLight;
            margin-bottom: 1rem;
        }
        .contact-p {
            text-align: center;
            font-size: 1.25rem;
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
