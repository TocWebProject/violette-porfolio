<template>
    <section id="home" class="hero-section">
        <div class="section-container" >
            <div class="hero-logo">
                <div class="polygon-container-red" >
                     <div class="circle-red" @mouseover="hoverCircleRed()" @mouseleave="reverseHoverCircleRed()">
                         <img class="img-circle-red" src="~/assets/img/test-vio-3.png"  alt="">
                     </div>
                </div>
                <div class="polygon-container-blue">
                    <div class="bar-blue" @mouseover="hoverBarBlue()" @mouseleave="reverseHoverBarBlue()">
                        <img class="img-bar-blue" src="~/assets/img/test-vio.png" alt="">
                    </div> 
                </div>
                <div class="polygon-container-yellow">
                    <div class="circle-yellow" @mouseover="hoverCircleYellow()" @mouseleave="reverseHoverCircleYellow()">
                        <img class="img-circle-yellow" src="~/assets/img/test-vio-2.png" alt="">
                    </div>
                </div>   
            </div>
            <div class="arrow-container">
                <div class="arrow-down" @click="scrollToLino()">
                    <svg xmlns="http://www.w3.org/2000/svg" class="arrow-svg h-6 w-6" fill="#000000" viewBox="0 0 24 24" stroke="currentColor">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 14l-7 7m0 0l-7-7m7 7V3" />
                    </svg>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    name:'HeroSection',
    methods: {
        heroAnim(){
            const gsap = this.$gsap
            const heroAnim = new gsap.timeline()
            
            heroAnim.from(".circle-red", {
                x: '-600%',
                duration: 1.7,
                ease: 'power1.inOut',
            },0)

            heroAnim.from(".bar-blue", {
                y: '-300%',
                duration: 1.7,
                ease: 'power1.inOut',
            },0.6)

            heroAnim.from(".circle-yellow", {
                x: '600%',
                duration: 1.7,
                ease: 'power1.inOut',
            },1.2)

            heroAnim.from(".arrow-container", {
                opacity: 0,
                duration: 1,
            },3.8)

        },

        scrollToLino() {
            const gsap = this.$gsap
            gsap.to(window, {scrollTo: {y:"#linogravures"}});
        },

        animateOnScroll() {
            const gsap = this.$gsap

            gsap.to(".arrow-down", {
                scrollTrigger: {
                    trigger: '.arrow-down',
                    start: 'top 85%',
                    toggleActions: "restart resume reverse reverse",
                    scrub: true, 
                },
                opacity: 0,
                duration: 0.3,
            })

            // gsap.to(".circle-red", {
            //     scrollTrigger: {
            //         trigger: '.hero-section',
            //         start: 'top top',
            //         toggleClass: 'active',
            //         toggleActions: "restart resume reverse reverse",
            //         scrub: true,
            //     },
            //     opacity: 0,
            // })

            // gsap.to(".bar-blue", {
            //     scrollTrigger: {
            //         trigger: '.hero-section',
            //         start: 'top top',
            //         toggleClass: 'active',
            //         toggleActions: "restart resume reverse reverse",
            //         scrub: true,
            //     },
            //     opacity: 0,
            // })

            // gsap.to(".circle-yellow", {
            //     scrollTrigger: {
            //         trigger: '.hero-section',
            //         start: 'top top',
            //         toggleClass: 'active',
            //         toggleActions: "restart resume reverse reverse",
            //         scrub: true,
                  
            //     },
            //     opacity: 0,
            // })

        },
        hoverCircleYellow() {
            const gsap = this.$gsap 
            const ExpoScaleEase = this.$ExpoScaleEase

            gsap.to(".img-circle-yellow", {
                opacity: 1,
                scale: 1,
                ease: ExpoScaleEase,
                duration: 0.4,
            })

            // gsap.to(".circle-yellow", {
            //     scale: 1.2,
            //     ease: ExpoScaleEase,
            //     duration: 0.4,
            // })
        },

        reverseHoverCircleYellow() {
            const gsap = this.$gsap 
            const ExpoScaleEase = this.$ExpoScaleEase

            gsap.to(".img-circle-yellow", {
               opacity: 0, 
               scale: 1.15,
               ease: ExpoScaleEase,
               duration: 0.4,
            })

            // gsap.to(".circle-yellow", {
            //     scale: 1,
            //     ease: ExpoScaleEase,
            //     duration: 0.4,
            // })
        },
        
        hoverBarBlue() {
            const gsap = this.$gsap 
            const ExpoScaleEase = this.$ExpoScaleEase

            gsap.to(".img-bar-blue", {
                opacity: 1,
                scale: 1.05,
                y: '-9px',
                ease: ExpoScaleEase,
                duration: 0.4,
            })

            // gsap.to(".bar-blue", {
            //     scale: 1.1,
            //     ease: ExpoScaleEase,
            //     duration: 0.4,
            // })
        },

        reverseHoverBarBlue() {
            const gsap = this.$gsap 
            const ExpoScaleEase = this.$ExpoScaleEase

            gsap.to(".img-bar-blue", {
               opacity: 0, 
               scale: 1,
               y: '0px',
               ease: ExpoScaleEase,
               duration: 0.4,
            })

            // gsap.to(".bar-blue", {
            //     scale: 1,
            //     ease: ExpoScaleEase,
            //     duration: 0.4,
            // })
        },

        hoverCircleRed() {
            const gsap = this.$gsap 
            const ExpoScaleEase = this.$ExpoScaleEase

            gsap.to(".img-circle-red", {
                opacity: 1,
                scale: 1,
                ease: ExpoScaleEase,
                duration: 0.4,
            })

            // gsap.to(".circle-red", {
            //     scale: 1.2,
            //     ease: ExpoScaleEase,
            //     duration: 0.4,
            // })
        },

        reverseHoverCircleRed() {
            const gsap = this.$gsap 
            const ExpoScaleEase = this.$ExpoScaleEase

            gsap.to(".img-circle-red", {
               opacity: 0, 
               scale: 1.15,
               ease: ExpoScaleEase,
               duration: 0.4,
            })

            // gsap.to(".circle-red", {
            //     scale: 1,
            //     ease: ExpoScaleEase,
            //     duration: 0.4,
            // })
        },

    },


    mounted(){
        this.heroAnim();
        this.animateOnScroll();
    }
}
</script>

<style lang="scss">
.hero-section {
    overflow: hidden !important;
    
    .section-container {
        position: relative;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
        height: 100vh;
        margin: 0 auto;
        max-width: 1600px;
        width: 100%; 
        margin-bottom: 100px;

        .hero-logo {
            width: 100%;
            display: flex;
            justify-content: center;
            align-items: center;
 
            .polygone-container-red, .polygone-container-blue, .polygone-container-yellow {
                display: flex;
                justify-content: center;
                align-items: center;
                overflow: hidden;
            }

            .circle-red {
                -webkit-clip-path: circle(50% at 50% 50%);
                clip-path: circle(50% at 50% 50%); 
                background-color: #be1e2d;
                width: 152px;
                height: 152px;
                overflow: hidden;

                .img-circle-red {
                    -webkit-clip-path: circle(50% at 50% 50%);
                    clip-path: circle(50% at 50% 50%); 
                    position: absolute;
                    top: 0;
                    left: 0;
                    opacity: 0;
                    width: 152px;
                    height: 152px;
                    transform: scale(1.15);
                }
            }

            .bar-blue {
                -webkit-clip-path: inset(0 30% 0 30%);
                clip-path: inset(0 30% 0 30%);
                background-color: #21409a;
                width: 300px;
                height: 650px;
                overflow: hidden;

                .img-bar-blue {
                    position: absolute;
                    top: 0;
                    left: 0;
                    opacity: 0;
                    width: 300px;
                    height: 785px;
                }
            }

            .circle-yellow {
                -webkit-clip-path: circle(50% at 50% 50%);
                clip-path: circle(50% at 50% 50%); 
                background-color: #ffde17;
                width: 152px;
                height: 152px;
                overflow: hidden;

                .img-circle-yellow {
                    -webkit-clip-path: circle(50% at 50% 50%);
                    clip-path: circle(50% at 50% 50%); 
                    position: absolute;
                    top: 0;
                    left: 0;
                    opacity: 0;
                    width: 152px;
                    height: 152px;
                    transform: scale(1.15);
                }
            }
        }

        .arrow-container {
            position: absolute;
            bottom: 25px;
            right: 40px;

            .arrow-down {   
                width: 33px;
                height: 33px;
                cursor: pointer;
            }
        }
    } 
}

@media screen and (min-width: 100px) and (max-width: 600px) { 
    .hero-section {
        .section-container  {
            .arrow-container {
                right: 18px;
                bottom: 60px;
            }

            .hero-logo {
                .circle-red {
                    width: 76px;
                    height: 76px;
                    .img-circle-red {
                        width: 76px;
                        height: 76px;
                    }
                }
                .bar-blue {
                    width: 150px;
                    height: 350px;

                    .img-bar-blue {
                    width: 150px;
                    height: 350px;
                    }
                }
                .circle-yellow {
                    width: 76px;
                    height: 76px;

                    .img-circle-yellow {
                        width: 76px;
                        height: 76px;
                    }
                }
            }
        }
    }
}

@media screen and (min-width: 1600px) { 
.hero-section {
        .section-container  {
            .arrow-container {
                right: 10%;
            }
        }
    } 
}
</style>