<template>
    <section id="linogravures" class="lino-section">
        <div class="section-container">
            <h1>Linogravures</h1>
                <div class="baigneuse-top" id="baigneuse"></div>
                <div class="baigneuse-container">
                    <NuxtLink class="link-img-baigneuse" to="/labaigneuse">
                        <div class="overlay-card-baigneuse"></div>
                        <img  class="img-baigneuse" src="~assets/img/violette-baigneuse-vase.png" width="478" height="597" alt="linogravure noir et bleu" loading="lazy">
                    </NuxtLink>
                    <NuxtLink class="link-baigneuse" to="/labaigneuse">La baigneuse</NuxtLink>
                </div>

                <div class="nues-top" id="nues"></div>
                <div class="nues-container">
                    <NuxtLink class="link-nues" to="/nues">Nues</NuxtLink>
                    <NuxtLink class="link-img-nues" to="/nues">
                        <div class="overlay-card-nues"></div>
                        <img  class="img-nues" src="~assets/img/violette-nues-plantes.png" width="478" height="597" alt="linogravure noir et bleu" loading="lazy">
                    </NuxtLink>
                </div>
            </div>
    </section>
</template>

<script>
export default {
    name:'LinoSection',
    methods: {
        animateOnScroll() {
            const gsap = this.$gsap

            gsap.to('.overlay-card-baigneuse', {
                scrollTrigger: {
                    trigger: '.overlay-card-baigneuse',
                    start: 'top 80%',
                    toggleClass: 'active',
                    toggleActions: "play reverse restart reverse",
                },
                ease: 'power0.inOut',
                height: 0,
            })

            gsap.to('.overlay-card-nues', {
                scrollTrigger: {
                    trigger: '.overlay-card-nues',
                    start: 'top 80%',
                    toggleClass: 'active',
                    toggleActions: "play reverse restart reverse",
                },
                ease: 'power0.inOut',
                height: 0,
            })
        }
    },

    mounted(){
        this.animateOnScroll();
    }
}
</script>

<style lang="scss">
.lino-section {
    background-color: #21409a;
    color: #ffffff;
    padding: 60px 0px 60px 0px;
  
    .section-container {
        margin: 0 auto;
        max-width: 1400px;
        height: auto;

        h1{
            margin: 50px 0px;
            text-align: center;
            font-size: 90px;
            color: #ffffff;
        }

        // BAIGNEUSE CARD
        .baigneuse-top {
            height: 50px;
        }

        .baigneuse-container {
            display: flex;
            justify-items: center;
            align-items: center;
            height: auto;
            margin-left: 99px;
            

            .link-baigneuse {
                margin-left: 80px;
                transform: translateY(-75px);
            }

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
        }

        // NUES CARD
        .nues-top {
            height: 50px;
            transform: translateY(-180px);
        }

        .nues-container {
            display: flex;
            justify-content: flex-end;
            justify-items: center;
            align-items: center;
            height: auto;
            margin-right: 99px;
          

            .link-nues {
                margin-right: 80px;
                transform: translateY(-75px);

            }

            .link-img-nues {
                position: relative;
                margin: 0px 20px;
                transform: translateY(-180px);
                
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

        }

        a {            
            text-decoration: none;
            color: white;
            font-size: 25px;

            &:link {
            color: white;
            }

            &:visited {
            color:whitesmoke;
            }

            &:hover {
            color: rgb(164, 185, 250);
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
        .section-container {   
            min-height: 700px;

            h1 {
                font-size: 40px;
                margin: 30px 0px;
            }

            // BAINGEUSE CARD
            .baigneuse-container{
                flex-direction: column;
                margin-left: 0px;
                margin-right: 0px;

                .link-baigneuse {
                    margin-left: 0px;
                    transform: translateY(0px);
                }
            }
            
            // NUES CARD
            .nues-top {
                transform: translateY(0px);
            }
            .nues-container { 
                flex-direction: column;
                margin-left: 0px;
                margin-right: 0px;

                .link-nues {
                    margin-right: 0px;
                    transform: translateY(0px);
                }

                .link-img-nues {
                    order: 1;
                    transform: translateY(0px);
                }

                .link-nues {
                    order: 2;
                }
            }
        }
    }
}
</style>