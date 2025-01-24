<script setup>
import GuestLayout from '@/Layouts/GuestLayout.vue';
import InputError from '@/Components/InputError.vue';
import InputLabel from '@/Components/InputLabel.vue';
import PrimaryButton from '@/Components/PrimaryButton.vue';
import TextInput from '@/Components/TextInput.vue';
import { Head, Link, useForm } from '@inertiajs/vue3';

const form = useForm({
    name: '',
    email: '',
    password: '',
    password_confirmation: '',
});

const submit = () => {
    form.post(route('register'), {
        onFinish: () => form.reset('password', 'password_confirmation'),
    });
};
</script>

<template>
    <GuestLayout style="width: 100%;">
        <Head title="Register" />
        
        <form @submit.prevent="submit">
            <img src="/img/login.png" alt="" class="img-container">
            <div class="form-container">
                <a href="/">
                    <img src="/img/openai-white-logomark.png" alt="" id="logo">
                </a>

                <div  class="mt-4">
                    <InputLabel for="name" value="Name" />

                    <TextInput
                        id="name"
                        type="text"
                        class="mt-1 block w-full"
                        v-model="form.name"
                        required
                        autofocus
                        autocomplete="name"
                    />

                    <InputError class="mt-2" :message="form.errors.name" />
                </div>

                <div class="mt-4">
                    <InputLabel for="email" value="Email" />

                    <TextInput
                        id="email"
                        type="email"
                        class="mt-1 block w-full"
                        v-model="form.email"
                        required
                        autocomplete="username"
                    />

                    <InputError class="mt-2" :message="form.errors.email" />
                </div>

                <div class="mt-4">
                    <InputLabel for="password" value="Password" />

                    <TextInput
                        id="password"
                        type="password"
                        class="mt-1 block w-full"
                        v-model="form.password"
                        required
                        autocomplete="new-password"
                    />

                    <InputError class="mt-2" :message="form.errors.password" />
                </div>

                <div class="mt-4">
                    <InputLabel
                        for="password_confirmation"
                        value="Confirm Password"
                    />

                    <TextInput
                        id="password_confirmation"
                        type="password"
                        class="mt-1 block w-full"
                        v-model="form.password_confirmation"
                        required
                        autocomplete="new-password"
                    />

                    <InputError
                        class="mt-2"
                        :message="form.errors.password_confirmation"
                    />
                </div>

                <div class="mt-4 flex items-center justify-end" style="flex-direction: row; align-items: center;">
                    <Link
                        :href="route('login')"
                        class="already"
                    >
                        Already registered?
                    </Link>

                    <PrimaryButton class="button-container"
                        :class="{ 'opacity-25': form.processing }"
                        :disabled="form.processing"
                    >
                        Register
                    </PrimaryButton>
                </div>
            </div>
        </form>
    </GuestLayout>
</template>

<style>
    form {
        display: flex;
        justify-content: space-evenly;
        align-items: end;
        width: 100%;
        max-width: 100%;
        max-height: 100%;
    }

    #logo {
        width: 3rem;
        height: 3rem;
        filter: invert(0.8);
        margin-bottom: 5rem;
    }

    .form-container {
        width: 50%;
        height: 100vh;
        margin: 0 auto;
        padding: 5rem;
        background-color: #fff;
        box-sizing: border-box;
        box-shadow: 0 0 50px rgba(0, 0, 0, 0.5);
        z-index: 2;
    }

    .form-container a, .form-container div {
        display: flex;
        flex-direction: column;
        align-items: end;
    }

    .button-container {
        margin: 1rem 0 1rem 1rem;
    }

    .img-container {
        width: 50%;
        height: 100vh;
        box-sizing: border-box;
        object-fit: cover;
    }
</style>