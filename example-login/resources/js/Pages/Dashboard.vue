<script setup>
import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
import { Head } from '@inertiajs/vue3';
</script>

<template>
    <Head title="Dashboard" />

    <AuthenticatedLayout>
        <template #header>
            <div style="height: 65px;"></div>
            <h2 class="text-xl font-semibold leading-tight text-gray-800">
                Dashboard
            </h2>
        </template>

        <img id="background" src="/img/ini_background_white.svg"/>

        <div class="content">
            <div class="mx-auto max-w-7xl sm:px-6 lg:px-8 margin">
                <div class="overflow-hidden bg-white shadow-sm sm:rounded-lg">
                    <div class="post">
                        <img src="/img/1-intro-photo-final.png" alt="" class="pfp">
                        <div class="vertical-separator"></div>
                        <div class="post-content">
                            <div style="display: flex; align-items: center;">
                                <h3>AI Revolutionizing Healthcare in 2025</h3>
                                <p style="font-size: 0.8rem; color: #aaa; margin: 0 2rem;">— January 24, 2025, 8:45 PM</p>
                            </div>
                            <div class="horizontal-separator"></div>
                            <p>AI is transforming healthcare by enabling early disease detection, personalized treatment, and efficient medical data management. With breakthroughs in AI-powered diagnostics, the future of patient care looks brighter than ever.</p>
                        </div>
                    </div>
                </div>
            </div>
            <div class="mx-auto max-w-7xl sm:px-6 lg:px-8 margin">
                <div class="overflow-hidden bg-white shadow-sm sm:rounded-lg">
                    <div class="post">
                        <div class="post-content">
                            <div style="display: flex; align-items: center;">
                                <h3>ChatGPT vs Traditional Search Engines</h3>
                                <p style="font-size: 0.8rem; color: #aaa; margin: 0 2rem;">— January 24, 2025, 4:00 AM</p>
                            </div>
                            <div class="horizontal-separator"></div>
                            <p>Why search through endless links when AI can give you direct answers? Conversational AI is reshaping how we access information, making it faster, smarter, and more intuitive. Is this the end of search engines as we know them?</p>
                            
                        </div>
                        <div class="vertical-separator"></div>
                        <img src="/img/a84aa310f33862e53c30f55bdf94b013.png" alt="" class="pfp">
                    </div>
                </div>
            </div>
            <div class="mx-auto max-w-7xl sm:px-6 lg:px-8 margin">
                <div class="overflow-hidden bg-white shadow-sm sm:rounded-lg">
                    <div class="post">
                        <img src="/img/pexels-photo-1704488.png" alt="" class="pfp">
                        <div class="vertical-separator"></div>
                        <div class="post-content">
                            <div style="display: flex; align-items: center;">
                                <h3>AI Artists: Creativity Meets Code</h3>
                                <p style="font-size: 0.8rem; color: #aaa; margin: 0 2rem;">— January 22, 2025, 1:30 PM</p>
                            </div>
                            <div class="horizontal-separator"></div>
                            <p>From painting to music, AI is blending creativity with technology. Tools like generative models are helping artists push boundaries, but will machines ever truly replace human imagination?</p>
                        </div>
                    </div>
                </div>
            </div>
            <div class="mx-auto max-w-7xl sm:px-6 lg:px-8 margin">
                <div class="overflow-hidden bg-white shadow-sm sm:rounded-lg">
                    <div class="post">
                        <div class="post-content">
                            <div style="display: flex; align-items: center;">
                                <h3>The Ethics of AI Surveillance</h3>
                                <p style="font-size: 0.8rem; color: #aaa; margin: 0 2rem;">— January 21, 2025, 11:45 AM</p>
                            </div>
                            <div class="horizontal-separator"></div>
                            <p>As AI-powered surveillance grows, so do concerns about privacy and misuse. Balancing security with individual rights is becoming one of the biggest challenges of our time. Where should we draw the line?</p>
                        </div>
                        <div class="vertical-separator"></div>
                        <img src="/img/images.png" alt="" class="pfp">
                    </div>
                </div>
            </div>
        </div>
    </AuthenticatedLayout>
</template>

<style scoped>
    h3 {
        font-size: 1.5rem;
        margin-left: 3rem;
    }

    p {
        margin: 2rem;
    }

    #background {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        object-fit: cover;
        z-index: -1;
    }

    .content {
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    .margin {
        margin: 2rem;
    }

    .post {
        height: 14rem;
        display: flex;
        align-items: center;
    }

    .post-content {
        padding: 2rem;
    }

    .pfp {
        width: 10rem;
        height: 10rem;
        margin: 2rem;
        border-radius: 5rem;
        box-shadow: 0 3px 5px 0 rgb(0 0 0 / 0.1);
    }

    .vertical-separator {
        width: 2px;
        height: 100%;
        margin: 3rem 0;
        background-color: #aaa;
    }

    .horizontal-separator {
        height: 2px;
        width: 100%;
        margin: 1rem;
        background-color: #aaa;
    }

    
</style>