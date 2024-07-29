<template>
    <section class="pk__small-text_section pk__section-margin-top pk__section-margin-bot">
        <div class="pk__container pk__m">
            <span class="pk__small-text_percent">28 Awards</span>
            <p>From national recognitions to editorial releases, we try our best to help your business shine above the mountain tops.</p>
            <Button href="#">Schedule Consultation</Button>
        </div>
    </section>
</template>

<script setup>
// Components
import Button from '@/components/Button.vue';

</script>

<style lang="scss">
@import "@/assets/_variables";

.pk__small-text_section {
    text-align: center;

    .pk__small-text_percent {
        font-size: 10vw;
        font-family: $heading-font-stack;
        line-height: 1;
        color: lighten($font-color, 70%);
    }

    p {
        font-weight: 300;
    }

    @media #{$m-and-up} {
        .pk__small-text_percent {
            font-size: 7.5vw;
        }
    }
 
    @media #{$l-and-up} {
        p {
            font-size: 1.5vw;
        }
    }
}
</style>