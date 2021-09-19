<template>
    <section id="linogravures" class="lino-section">
        <div class="section-container">
            <h1 class="h1-linogravure">
                Linogravures
            </h1>

            <div class="top" id="baigneuse"></div>  
            <article class="baigneuse-container">
                <NuxtLink class="link-img-baigneuse" to="/labaigneuse">
                        <div class="overlay-card-baigneuse"></div>
                        <img 
                            class="img-baigneuse" 
                            src="~assets/img/violette-baigneuse-vase.png" 
                            width="478" 
                            height="597" 
                            alt="linogravure noir et bleu" 
                            loading="lazy"
                            title="Violette Le Moal - Linogravure nommée La Baigneuse"

                        >        
                </NuxtLink>
                <div class="baigneuse-text"    
                >
                    <h3 >La baigneuse</h3>
                    <NuxtLink class="link-baigneuse" to="/labaigneuse">voir plus</NuxtLink>
                </div>
            </article>

            <div class="top" id="nues"></div>
            <article class="nues-container">
                <div class="nues-text">
                    <h3>Nues</h3>
                    <NuxtLink class="link-nues" to="/nues">voir plus</NuxtLink>
                </div>
                <NuxtLink class="link-img-nues" to="/nues">
                        <div class="overlay-card-nues"></div>
                        <img  
                            class="img-nues" 
                            src="~assets/img/violette-nues-plantes.png"
                            width="478" 
                            height="597" 
                            alt="linogravure noir et bleu" 
                            loading="lazy"
                            title="Violette Le Moal - Linogravure nommée Nues"

                        >   
                </NuxtLink>
            </article>

            <div class="top" id="cormoran"></div>  
            <article class="cormoran-container">
                <NuxtLink class="link-img-cormoran" to="/cormoran">
                        <div class="overlay-card-cormoran"></div>
                        <img 
                            class="img-cormoran" 
                            src="~assets/img/violette-cormoran.png" 
                            width="478" 
                            height="597" 
                            alt="linogravure noir et bleu" 
                            loading="lazy"
                            title="Violette Le Moal - Linogravure nommée Cormoran"
                        >        
                </NuxtLink>
                <div class="cormoran-text">
                        <h3 >Cormoran</h3>
                        <NuxtLink class="link-cormoran" to="/cormoran">voir plus</NuxtLink>
                </div>
            </article>

            <div class="top" id="songeuse"></div>
            <article class="songeuse-container">
                <div class="songeuse-text">
                    <h3>La songeuse</h3>
                    <NuxtLink class="link-songeuse" to="/songeuse">voir plus</NuxtLink>
                </div>
                <NuxtLink class="link-img-songeuse" to="/songeuse">
                        <div class="overlay-card-songeuse"></div>
                        <img  
                            class="img-songeuse" 
                            src="~assets/img/violette-songeuse.png"
                            width="478" 
                            height="597" 
                            alt="linogravure noir et bleu" 
                            loading="lazy"
                            title="Violette Le Moal - Linogravure nommée Songeuse"
                        >   
                </NuxtLink>
            </article>
        </div>
    </section>
</template>

<script>
export default {
    name:'LinoSection',
    methods: {
        animateImgOnScroll() {
            const gsap = this.$gsap

            gsap.to('.overlay-card-baigneuse', {
                ease: 'power0.inOut',
                height: '0%',
                scrollTrigger: {
                    trigger: '.baigneuse-container',
                    start: "top 60%",
                    toggleActions: "restart complete none reverse",
                },
            })

            gsap.to('.overlay-card-nues', {
                ease: 'power0.inOut',
                height: '0%',
                scrollTrigger: {
                    trigger: '.nues-container',
                    start: "top 60%",
                    toggleActions: "restart complete none reverse",
                },
            })

            gsap.to('.overlay-card-cormoran', {
                ease: 'power0.inOut',
                height: '0%',
                scrollTrigger: {
                    trigger: '.cormoran-container',
                    start: "top 70%",
                    toggleActions: "restart complete none reverse",
                },
            })

              gsap.to('.overlay-card-songeuse', {
                ease: 'power0.inOut',
                height: '0%',
                scrollTrigger: {
                    trigger: '.songeuse-container',
                    start: "top 90%",
                    toggleActions: "restart complete none reverse"
                },
            })
        },

        animateTitleOnScroll() {
            const gsap = this.$gsap

            this.$ScrollTrigger.matchMedia({
                // Extra Desktop
                "(min-width: 1220px)": function() {
                    gsap.to('.baigneuse-text', {
                        scrollTrigger: {
                        trigger: '.baigneuse-container',
                        start: 'top 50%',
                        scrub: true,
                        toggleActions: "restart resume reverse reverse"
                        },
                        // ease: "power1.inOut",
                        y : '-120px',
                    });

                    gsap.to('.nues-text', {
                        scrollTrigger: {
                        trigger: '.nues-container',
                        start: 'top 50%',
                        scrub: true,
                        toggleActions: "restart resume reverse reverse"
                        },
                        // ease: "power1.inOut",
                        y : '-120px',
                    });

                    gsap.to('.cormoran-text', {
                        scrollTrigger: {
                        trigger: '.cormoran-container',
                        start: 'top 50%',
                        scrub: true,
                        toggleActions: "restart resume reverse reverse"
                        },
                        // ease: "power1.inOut",
                        y : '-120px',
                    });

                    gsap.to('.songeuse-text', {
                        scrollTrigger: {
                        trigger: '.songeuse-container',
                        start: 'top 50%',
                        scrub: true,
                        toggleActions: "restart resume reverse reverse"
                        },
                        // ease: "power1.inOut",
                        y : '-120px',
                    });
                },

                // Extra Desktop
                "(max-width: 1219px)": function() {
                    gsap.to('.baigneuse-text', {
                        scrollTrigger: {
                        trigger: '.baigneuse-container',
                        start: 'top bottom',
                        scrub: true,
                        toggleActions: "restart resume reverse reverse"
                        },
                        // ease: "power1.inOut",
                        y : '-90px',
                    });

                    gsap.to('.nues-text', {
                        scrollTrigger: {
                        trigger: '.nues-container',
                        start: 'top bottom',
                        scrub: true,
                        toggleActions: "restart resume reverse reverse"
                        },
                        // ease: "power1.inOut",
                        y : '-90px',
                    });

                    gsap.to('.cormoran-text', {
                        scrollTrigger: {
                        trigger: '.cormoran-container',
                        start: 'top bottom',
                        scrub: true,
                        toggleActions: "restart resume reverse reverse"
                        },
                        // ease: "power1.inOut",
                        y : '-90px',
                    });

                    gsap.to('.songeuse-text', {
                        scrollTrigger: {
                        trigger: '.songeuse-container',
                        start: 'top bottom',
                        scrub: true,
                        toggleActions: "restart resume reverse reverse"
                        },
                        // ease: "power1.inOut",
                        y : '-90px',
                    });
                },
            });
        }
    },

    mounted(){
        this.animateImgOnScroll();
        this.animateTitleOnScroll();
    }
}
</script>

<style lang="scss">
.lino-section {
    background-color: #21409a;
    color: #ffffff;
    padding: 40px 0px 80px 0px;

    .section-container {
        margin: 0 auto;
        max-width: 1400px;
        height: auto;
        // Compenser les transform translaye Y des articles.
        margin-bottom: -300px;
        h1 {
            margin: 50px 0px 0px;
            text-align: center;
            font-size: 90px;
            color: #ffffff;
        }

        .top {
            height: 100px;
        }

        // BAIGNEUSE CARD + CORMORAN CARD
        .baigneuse-container, .cormoran-container {
            display: flex;
            justify-items: center;
            align-items: flex-end;
            height: auto;
            margin-left: 99px;

            &.cormoran-container {
                transform: translateY(-300px);
            }
            
            .baigneuse-text, .cormoran-text {
                margin-left: 90px;
                margin-bottom: 180px;

                h3 {
                    font-weight: 400;
                    font-size: 35px;
                }

                .link-baigneuse, .link-cormoran {
                    font-size: 16px;
                    letter-spacing: 1px;
                    margin-top: 3px;
                }
                
            }

            // LINK IMG BAIGNEUSE
            .link-img-baigneuse {
                position: relative;
                margin: 0px 20px;
                overflow: visible;
                
                .img-baigneuse {
                    max-width: 100%;
                    height: auto;
                }
                .overlay-card-baigneuse {
                    position: absolute;
                    top: 0;
                    left: 0;
                    width: 100%;
                    height: 100%;
                    background-color: #2849ac;
                }
            }

            // IMG LINK CORMORAN
            .link-img-cormoran {
                position: relative;
                margin: 0px 20px;
                overflow: visible;
                
                .img-cormoran {
                    max-width: 100%;
                    height: auto;
                }

                .overlay-card-cormoran {
                    position: absolute;
                    top: 0;
                    left: 0;
                    width: 100%;
                    height: 100%;
                    background-color: #2849ac;
                }
            }
    
        }

        .nues-container, .songeuse-container {
            display: flex;
            justify-content: flex-end;
            justify-items: center;
            align-items: flex-end;
            height: auto;
            margin-right: 99px;

            &.nues-container {
                transform: translateY(-150px);
            }

            &.songeuse-container {
                transform: translateY(-450px);
            }

            .nues-text, .songeuse-text {
                margin-right: 90px;
                margin-bottom: 180px;


                h3 {
                    font-weight: 400;
                    font-size: 35px;
                }

                .link-nues, .link-songeuse {
                    font-size: 16px;
                    letter-spacing: 1px;
                    margin-top: 3px;     
                }
            }
            
            .link-img-nues {
                position: relative;
                margin: 0px 20px;
                
                .img-nues {
                    max-width: 100%;
                    height: auto;
                }
                .overlay-card-nues {
                    position: absolute;
                    top: 0;
                    left: 0;
                    width: 100%;
                    height: 100%;
                    background-color: #2849ac;
                }
            }

            .link-img-songeuse {
                position: relative;
                margin: 0px 20px;
                
                .img-songeuse {
                    max-width: 100%;
                    height: auto;
                }
                .overlay-card-songeuse {
                    position: absolute;
                    top: 0;
                    left: 0;
                    width: 100%;
                    height: 100%;
                    background-color: #2849ac;
                }
            }

        }

        a {            
            text-decoration: underline 1px;
            color: white;
            font-size: 17px;
            transition: all 0.3s ease-out;

            &:link {
            color: white;
            }

            &:visited {
            color:whitesmoke;
            }

            &:hover {
            color: rgb(169, 189, 250);
            }

            &:active {
            color: rgb(148, 173, 247);
            }
        }
    }
    
}


// // Extra small devices (portrait phones, tablet, desktop less than 1220px)
@media screen and (min-width: 100px) and (max-width: 1220px) { 
    .lino-section {
        padding: 50px 0px 200px 0px;
        min-height: 700px;

        .section-container {
            margin-bottom: 0px;

            h1 {
                font-size: 44px;
                margin: 30px 0px 10px 0px;
            }

            // BAINGEUSE CARD + CORMORAN CARD
            .baigneuse-container, .cormoran-container{
                position: relative;
                align-items: center;
                flex-direction: column;
                margin-left: 0px;
                margin-right: 0px;
                margin-bottom: 80px;

                &.cormoran-container {
                    transform: translateY(0px);
                 }

                .baigneuse-text, .cormoran-text {
                    position: absolute;
                    bottom: -340px;
                    width: auto;
                    margin-top: 20px;
                    margin-right: auto;
                    margin-left: auto;
                    z-index: 2;

                }
            }
            
            // NUES CARD
            .nues-container, .songeuse-container { 
                position: relative;
                flex-direction: column;
                align-items: center;
                margin-left: 0px;
                margin-right: 0px;
                margin-bottom: 80px;

                &.nues-container {
                transform: translateY(0);
                }

                &.songeuse-container {
                    transform: translateY(0px);
                }

                .nues-text, .songeuse-text {
                    position: absolute;
                    bottom: -340px;
                    width: auto;
                    margin-left: auto;
                    margin-right: auto;
                    margin-top: 20px;
                    margin-right: 0px;
                    z-index: 2;
                }
            }
        }
    }
}

</style>