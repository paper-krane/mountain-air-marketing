<script setup>
import gsap from 'gsap';
import { ref, onMounted, onUnmounted } from 'vue';

// Images
import logo1 from '@/assets/images/logo-01.webp';
import logo2 from '@/assets/images/logo-02.webp';
import logo3 from '@/assets/images/logo-03.webp';
import logo4 from '@/assets/images/logo-04.webp';
import logo5 from '@/assets/images/logo-05.webp';

// Ref's 
const ctx = ref(null);

// On Component Mount
onMounted(() => {
    ctx.value = gsap.context(() => {
        const tl = gsap.timeline();

        tl.to('.pk__trust-bar_wrap', {
            duration: 50,
            x: '-100%',
            ease: 'linear',
            repeat: -1
        })
    });
});
</script>


<template>
    <section class="pk__trust-bar_section pk__section-margin-top pk__section-margin-bot">
        <div class="pk__trust-bar_container">
            <div class="pk__trust-bar_wrap">
                <div class="pk__trust-bar_logo-wrap">
                    <figure class="pk__trust-bar_logo">
                        <img :src="logo1" alt="Logo 1">
                    </figure>
                </div>
                <div class="pk__trust-bar_logo-wrap">
                    <figure class="pk__trust-bar_logo">
                        <img :src="logo2" alt="Logo 2">
                    </figure>
                </div>
                <div class="pk__trust-bar_logo-wrap">
                    <figure class="pk__trust-bar_logo">
                        <img :src="logo3" alt="Logo 3">
                    </figure>
                </div>
                <div class="pk__trust-bar_logo-wrap">
                    <figure class="pk__trust-bar_logo">
                        <img :src="logo4" alt="Logo 4">
                    </figure>
                </div>
                <div class="pk__trust-bar_logo-wrap">
                    <figure class="pk__trust-bar_logo">
                        <img :src="logo5" alt="Logo 5">
                    </figure>
                </div>
            </div>
            <div class="pk__trust-bar_wrap">
                <div class="pk__trust-bar_logo-wrap">
                    <figure class="pk__trust-bar_logo">
                        <img :src="logo1" alt="Logo 1">
                    </figure>
                </div>
                <div class="pk__trust-bar_logo-wrap">
                    <figure class="pk__trust-bar_logo">
                        <img :src="logo2" alt="Logo 2">
                    </figure>
                </div>
                <div class="pk__trust-bar_logo-wrap">
                    <figure class="pk__trust-bar_logo">
                        <img :src="logo3" alt="Logo 3">
                    </figure>
                </div>
                <div class="pk__trust-bar_logo-wrap">
                    <figure class="pk__trust-bar_logo">
                        <img :src="logo4" alt="Logo 4">
                    </figure>
                </div>
                <div class="pk__trust-bar_logo-wrap">
                    <figure class="pk__trust-bar_logo">
                        <img :src="logo5" alt="Logo 5">
                    </figure>
                </div>
            </div>
        </div>
    </section>
</template>


<style lang="scss">
@import "@/assets/_variables";

.pk__trust-bar_section {
    overflow: hidden;

    .pk__trust-bar_container {
        white-space: nowrap;
    }

    .pk__trust-bar_wrap {
        display: inline-block;
        white-space: nowrap;

        .pk__trust-bar_logo-wrap {
            display: inline-block;
            width: 30vw;
            flex: none;
            margin-right: 15vw;

            figure {
                padding: 0;
                max-width: 200px;
                margin: 0 auto;
            }
        }
    }

    @media #{$m-and-up} {
        .pk__trust-bar_wrap {
            .pk__trust-bar_logo-wrap {
                width: 24vw;
                flex: none;
                margin-right: 12vw;
            }
        }
    }

    @media #{$l-and-up} {
        .pk__trust-bar_wrap {
            .pk__trust-bar_logo-wrap {
                width: 20vw;
                margin-right: 12vw;
            }
        }
    }

    @media #{$xl-and-up} {
        .pk__trust-bar_wrap {
            .pk__trust-bar_logo-wrap {
                width: 20vw;
                margin-right: 8vw;
            }
        }
    }

    @media #{$xxl-and-up} {
        .pk__trust-bar_wrap {
            .pk__trust-bar_logo-wrap {
                width: 18vw;
                margin-right: 6vw;
            }
        }
    }
}
</style>