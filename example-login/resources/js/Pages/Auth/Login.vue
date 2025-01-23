<script setup>
import Checkbox from '@/Components/Checkbox.vue';
import GuestLayout from '@/Layouts/GuestLayout.vue';
import InputError from '@/Components/InputError.vue';
import InputLabel from '@/Components/InputLabel.vue';
import PrimaryButton from '@/Components/PrimaryButton.vue';
import TextInput from '@/Components/TextInput.vue';
import { Head, Link, useForm } from '@inertiajs/vue3';

defineProps({
    canResetPassword: {
        type: Boolean,
    },
    status: {
        type: String,
    },
});

const form = useForm({
    email: '',
    password: '',
    remember: false,
});

const submit = () => {
    form.post(route('login'), {
        onFinish: () => form.reset('password'),
    });
};
</script>

<template>
    <GuestLayout style="width: 100%;">
        <Head title="Log in" />

        <form @submit.prevent="submit" class="container">
            <div class="form-container">
                <a href="/">
                    <img src="/img/openai-white-logomark.png" alt="" id="logo">
                </a>

                <div>
                    <InputLabel for="email" value="Email" />

                    <TextInput
                        id="email"
                        type="email"
                        class="mt-1 block w-full"
                        v-model="form.email"
                        required
                        autofocus
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
                        autocomplete="current-password"
                    />

                    <InputError class="mt-2" :message="form.errors.password" />
                </div>

                <div class="mt-4 block">
                    <label class="flex items-center">
                        <Checkbox name="remember" v-model:checked="form.remember" />
                        <span class="ms-2 text-sm text-gray-600"
                            >Remember me</span
                        >
                    </label>
                </div>

                <div class="flex items-center justify-start ">
                    <PrimaryButton class="button-container"
                        :class="{ 'opacity-25': form.processing} "
                        :disabled="form.processing"
                    >
                        Log in
                    </PrimaryButton>

                    <Link
                        v-if="canResetPassword"
                        :href="route('password.request')"
                        class="rounded-md text-sm text-gray-600 underline hover:text-gray-900 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2"
                    >
                        Forgot your password?
                    </Link>
                </div>
            </div>
            <img src="/img/3d-locked-padlock.png" alt="" class="img-container">
        </form>
    </GuestLayout>
</template>

<style scoped>
    form {
        display: flex;
        justify-content: space-evenly;
        align-items: start;
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

    .button-container {
        margin: 1rem 1rem 1rem 0;
    }

    .img-container {
        width: 50%;
        height: 100vh;
        box-sizing: border-box;
        object-fit: cover;
    }
</style>