<div class="wrap contact-wrap" id="kontakt">
    <h4 class="text-large">Kontakt</h4>
    <div class="contact-info">
        <div class="identification">
            <p class="text">Tomáš Otruba</p>
            <p class="text">IČ: 704 62 810</p>
        </div>
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
</div>

<style lang="scss" scoped>
    @import "../styles/vars.scss";
    .contact-wrap {
        
        .text-large {
            text-align: center;
            color: $systemLight;
            margin-bottom: 1rem;
        }
        .contact-info {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            gap: 1rem;
        }
        .text {
            text-align: center;
        }

        .contacts {
            // margin-top: 1rem;
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
    @media only screen and (min-width: 1024px) {
        .contact-wrap {
            // flex-direction: row;
            // flex-wrap: wrap;
            // align-items: center;
            // justify-content: center;
            gap: 2rem;
            // .text-large {
            //     width: 100%;
            // }
            .contact-info {
                flex-direction: row;
                gap: 6rem;
            }
        }
    }
</style>
