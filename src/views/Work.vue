<template>
    <div id="work" class="wrapper">

        <div class="static-container">
            <h1 class="title">
                work<br v-if="viewport.is568">(<span class="params">'selected'</span>)
            </h1>

            <div class="std">
                <p class="-gray">// Some special projects explained in details. Coming in a few days</p>


            </div>
        </div>

    </div>
</template>

<script>
    // styles
    import '@/styles/work.scss';

    export default {
        name: 'work',
        props: {
            viewport: Object,
        },
        data() {
            return {
                intro: new TimelineMax()
            }
        },
        methods: {},
        mounted() {

            /**
             * @desc
             * Intro scene
             */
            this.intro
                .addLabel('enter', 1)
                .from('.title', 2, {
                    autoAlpha: 0,
                    rotationX: 70,
                    transformOrigin: '50% 50% -100px',
                    ease: Power3.easeOut,
                }, 'enter')
                .from('.std', 2, {
                    autoAlpha: 0,
                    x: -32,
                    ease: Power3.easeOut,
                }, 'enter+=1.5');

        },
    };
</script>
