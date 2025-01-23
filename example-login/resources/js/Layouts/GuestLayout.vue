<script setup>
import ApplicationLogo from '@/Components/ApplicationLogo.vue';
import { Link } from '@inertiajs/vue3';
</script>

<template>
    <!-- <div>
        <Link href="/">
            <ApplicationLogo class="h-20 w-20 fill-current text-gray-500" />
        </Link>
    </div> -->

    <div class="form-continner">
        <slot />
    </div>
</template>

<style scoped>
    body {
        width: 100%;
    }

    .form-continner {
        margin: 0;
        padding: 0;

        width: 100%;
        
        background-color: white;

        display: flex;
    }
</style>
