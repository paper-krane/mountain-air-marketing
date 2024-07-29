<script setup>
import gsap from 'gsap';
import { ScrollTrigger } from 'gsap/all';
import { RouterLink } from 'vue-router';
import { ref, onMounted } from 'vue';

// Images
import image1 from '@/assets/design-17.png';
import image2 from '@/assets/1.webp';
import image3 from '@/assets/design-13.png';

// Ref's
const categoriesContainerRef = ref(null);
const ctx = ref(null);

// On Component Mount
onMounted(() => {
    gsap.registerPlugin(ScrollTrigger);

    ctx.value = gsap.context(() => {
        gsap.set('.pk__categories_link-container', {
            y: 40,
            opacity: 0,
        });
        gsap.to('.pk__categories_link-container', {
            duration: 2.4,
            y: 0,
            opacity: 1,
            stagger: 0.15,
            ease: 'power4.out',
            scrollTrigger: {
                trigger: categoriesContainerRef.value,
                start: 'top 70%',
            },
        });
    });
});
</script>


<template>
    <section class="pk__categories_section pk__section-margin-top pk__section-margin-bot">
        <div class="pk__container" ref="categoriesContainerRef">
            <h4>Our process is simple...</h4>
            <RouterLink to="#" class="pk__categories_link-container">
                <div class="pk__categories_link-image">
                    <figure>
                        <img :src="image1" alt="" style="object-position: 35% 50%;" />
                    </figure>
                </div>
                <div class="pk__categories_link-content">
                    <h4>01. Discovery Call</h4>
                    <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit.</p>
                </div>
            </RouterLink>
            <RouterLink to="#" class="pk__categories_link-container">
                <div class="pk__categories_link-image">
                    <figure>
                        <img :src="image2" alt="" style="object-position: 30% 50%;" />
                    </figure>
                </div>
                <div class="pk__categories_link-content">
                    <h4>02. Design & Strategize</h4>
                    <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit.</p>
                </div>
            </RouterLink>
            <RouterLink to="#" class="pk__categories_link-container">
                <div class="pk__categories_link-image">
                    <figure>
                        <img :src="image3" alt="" />
                    </figure>
                </div>
                <div class="pk__categories_link-content">
                    <h4>03. Implementation</h4>
                    <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit.</p>
                </div>
            </RouterLink>
        </div>
    </section>
</template>


<style lang="scss">
@import "@/assets/_variables";

.pk__categories_section {
    overflow: hidden;

    .pk__container {
        display: grid;
        grid-template-columns: repeat(2, 1fr);
        gap: 1rem;

        &> h4 {
            grid-column: span 2;
            margin-bottom: 0;
            padding-bottom: 1rem;
        }

        .pk__categories_link-container,
        .pk__categories_link-container:visited {
            display: block;
            position: relative;
            overflow: hidden;
            text-decoration: none;
            color: $white;
            transition: none;

            .pk__categories_link-image {
                aspect-ratio: 3 / 4;
                position: relative;
                overflow: hidden;
                border-radius: $border-radius;
                background-color: darken($site-bg, 5%);

                figure {
                    margin: 0;
                    position: absolute;
                    top: 0;
                    left: 0;
                    width: 100%;
                    height: 100%;

                    img {
                        width: 100%;
                        height: 100%;
                        object-fit: cover;
                        object-position: 50% 50%;
                    }
                }
            }

            &:nth-child(2) {
                grid-column: span 2;
            }

            .pk__categories_link-content {
                padding: 1rem;
                background-color: transparent;
                border-radius: $border-radius;
                position: absolute;
                left: 0;
                bottom: 0;
                width: 100%;
                z-index: 1;
                backdrop-filter: blur(6px);
                -webkit-backdrop-filter: blur(6px);

                h4 {
                    font-size: 1.25rem;
                    margin-bottom: .5rem;
                }

                p {
                    display: none;
                }
            }
        }
    }

    @media #{$l-and-up} {
        .pk__container {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 1rem;

            h4 {
                grid-column: span 3;
            }

            .pk__categories_link-container,
            .pk__categories_link-container:visited {
                display: grid;
                grid-template-columns: 120px 1fr;
                gap: 1rem;
                align-items: center;
                color: $font-color;
                border-radius: $border-radius;
                background-color: darken($site-bg, 4%);
                padding-right: 40px;

                &:nth-child(2) {
                    grid-column: span 1;
                }

                .pk__categories_link-image {
                    aspect-ratio: 2 / 3;
                    border-radius: $border-radius 0 0 $border-radius;

                    figure {
                        img {
                            transition: all 1s ease;
                        }
                    }
                }

                .pk__categories_link-content {
                    position: relative;
                    backdrop-filter: none;
                    -webkit-backdrop-filter: none;

                    p {
                        font-size: .875rem;
                        font-weight: 300;
                        display: block;
                        color: lighten($font-color, 40%);
                    }
                }
            }

            .pk__categories_link-container:hover,
            .pk__categories_link-container:focus {
                .pk__categories_link-image {
                    figure {
                        img {
                            transform: scale(1.1);
                        }
                    }
                }
            }
        }
    }

    @media #{$xl-and-up} {
        .pk__container {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 2rem;

            .pk__categories_link-container {
                grid-template-columns: 200px 1fr;

                .pk__categories_link-image {
                    aspect-ratio: 3 / 4;
                }
            }
        }
    }
}
</style>