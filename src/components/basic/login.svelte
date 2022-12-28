<script lang="ts">
    import { slide } from "svelte/transition";
    import SystemButton from "../small/systemButton.svelte";
    import Form from "./form.svelte";
    let register: boolean = false;
</script>

<div class="wrap login-wrap page-land">
    <div class="login-back" />
    <div class="login-inner">
        <img src="/img/sys/logo-dark.png" alt="logo" />
        {#if !register}
            <h4 class="text-large">Přihlásit se</h4>
            <Form
                ids="login"
                inputs={["Email"]}
                pwds={["Heslo"]}
                checkboxes={["Zapamatovat"]}
                type="outer"
                buttonText="Přihlásit se"
            />
        {:else}
            <h4 class="text-large">Zaregistrovat se</h4>
            <Form
                ids="register"
                inputs={["Jméno", "Příjmení", "Email"]}
                pwds={["Heslo", "Zopakovat heslo"]}
                checkboxes={["Zapamatovat"]}
                type="outer"
                buttonText="Zeregistrovat se"
            />
        {/if}
        <!-- svelte-ignore a11y-click-events-have-key-events -->
        <a
            href="/login"
            on:click={() => (register = !register)}
            class="text login-changer"
        >
            {register ? "Přihlásit se" : "Zaregistrovat se"}
        </a>
    </div>
</div>

<style lang="scss">
    @import "../../styles/vars.scss";
    .login-wrap {
        padding: 2rem 1rem 0;
        background-color: #03bab3;
        margin-bottom: 0;
        background-image: url("/img/login/wave.svg");
        background-repeat: no-repeat;
        background-size: 900px;
        background-position: bottom;
        // background-position: 10px 20px;
    }
    .login-inner {
        display: flex;
        flex-direction: column;
        align-items: center;
        background-color: white;
        border-radius: 30px;
        padding: 1rem;
        margin-top: 2rem;
        margin-bottom: 2.5rem;
        gap: 1rem;
    }
    .login-changer {
        color: $systemMedium;
        // margin-top: 1rem;
        transition: 0.25s ease;
        &:hover {
            cursor: pointer;
            scale: 1.1;
        }
    }
    @media only screen and (min-width: 768px) {
        .login-wrap {
            padding: 2rem 2rem 0;
            justify-content: center;
            align-items: center;
            background-size: 1200px;
        }
        .login-inner {
            padding: 3rem;
            width: calc(600px - 3rem);
        }
    }
    @media only screen and (min-width: 1024px) {
        .login-wrap{
            background-size: 110%;
            // background-: ;
        }
        .login-inner {
            width: calc(800px - 3rem);
        }
    }
</style>
