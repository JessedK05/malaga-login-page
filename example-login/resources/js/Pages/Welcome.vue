<script setup>
import { Head, Link } from '@inertiajs/vue3';

defineProps({
    canLogin: {
        type: Boolean,
    },
    canRegister: {
        type: Boolean,
    },
    laravelVersion: {
        type: String,
        required: true,
    },
    phpVersion: {
        type: String,
        required: true,
    },
});

function handleImageError() {
    document.getElementById('screenshot-container')?.classList.add('!hidden');
    document.getElementById('docs-card')?.classList.add('!row-span-1');
    document.getElementById('docs-card-content')?.classList.add('!flex-row');
    document.getElementById('background')?.classList.add('!hidden');
}
</script>

<template>
    <Head title="Welcome"/>
    <img id="background" src="/img/ini_background.svg"/>
    <div class="sub-container">
        <img src="/img/openai-white-logomark.png" alt="" id="logo">
        <h1 class="text-center text-sm title">Welcome</h1>
        <nav v-if="canLogin" class="log-container">
            <p style="color:white; letter-spacing: 5px">··················</p>
            <Link v-if="$page.props.auth.user" :href="route('dashboard')" class="log-link">Dashboard</Link>

            <template v-else>
                <Link :href="route('login')" class="log-link">Log-in</Link>

                <Link v-if="canRegister" :href="route('register')" class="log-link">Register</Link>
            </template>
            <p style="color:white; letter-spacing: 5px">··················</p>
        </nav>
        <footer class="py-16 text-center text-sm text-black dark:text-white/70">
            Laravel v{{ laravelVersion }} (PHP v{{ phpVersion }})
        </footer>
    </div>
</template>

<style scoped>
    @import url('https://fonts.cdnfonts.com/css/ailerons');

    * {
        margin: 0;
        padding: 0;
    }

    #background {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        object-fit: cover;
        z-index: -1;
    }

    .sub-container {
        min-width: 30rem;
        margin: 5rem auto;
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 3rem;
    }

    #logo {
        width: 3rem;
        height: 3rem;
        margin: 1rem;
    }

    .title {
        font-size: 4rem;
        color: #fff;
        font-family: "Ailerons";
        font-weight: 100;
    }

    .log-container {
        color: #fff;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        align-items: center;
        gap: 2rem;
    }

    .log-link {
        color: #aaa;
        text-transform: uppercase;
        font-family: Figtree,ui-sans-serif,system-ui,sans-serif,"Apple Color Emoji","Segoe UI Emoji",Segoe UI Symbol,"Noto Color Emoji";
        font-size: 1.3rem;
        letter-spacing: 2px;
        transition: all 0.5s ease-in-out;
    }

    .log-link:hover {
        color: #fff;
        font-weight: 700;
        letter-spacing: 4px;
    }
</style>